---
title: "Project MINI-V: AIDL과 Android Service"
date: "June 6. 2026"
tag: ["Android","AIDL","AOSP","Service"]
isPinned: false
url: "260606-miniv-android-aidl-service"
---

MINI-V Android 프로젝트의 AI Service 구현을 위해 Android AIDL에 대해 알아보았습니다.

# AIDL

AIDL(Android Interface Definition Language)은 Android System에서의 IPC 통신을
일반적인 OOP에서의 Interface처럼 편하게 사용할 수 있도록 자동 생성해주는 도구입니다.

Android 개발에서 사용하는 Kotlin/Java Interface는 같은 프로세스 안에서만 동작합니다.
프로세스가 다르면 OS가 메모리를 격리시켜 관리하기 때문에, 서로 다른 프로세스의 객체를 직접 참조하는 것이 불가능합니다.

AIDL은 이 한계를 넘어서기 위해 Serialization과 IPC Binder 관련 코드를 자동으로 생성해주는 역할을 합니다.
<br/>
<br/>

# AIDL, Stub, Proxy
AIDL의 기본적인 구성 요소로는 AIDL, Stub, Proxy가 있습니다.

## AIDL
위에서 언급한 내용과 같이, IPC 통신을 Interface를 이용해 간단하게 정의하는 것입니다.

MINI-V Android 프로젝트에서는 LLM Inference를 요청하는 AI Service AIDL과
그 결과를 받아 처리하는 Callback AIDL을 정의하였습니다.

#### IMINIVAIService.aidl
```java
interface IMINIVAIService {
    boolean isReady();
    int inferStream(String prompt, int maxTokens, ILLMStreamCallback callback);
    void cancel(int sessionId);
    String getModelInfo();
}
```

#### ILLMStreamCallback.aidl
```java
oneway interface ILLMStreamCallback {
    void onToken(int sessionId, String token);
    void onComplete(int sessionId);
    void onError(int sessionId, int code, String message);
}
```

여기서, `ILLMStreamCallback`은 특이하게도 `oneway interface`로 선언되어 있는데요,
이 `oneway` 키워드를 붙여 AIDL을 선언하게 되면, Asynchronous로 동작하기 때문에, 호출부가 Blocking되지 않습니다.<br/>
`oneway interface`의 특징으로는 반드시 반환값이 없는 `void` 타입이어야 한다는 점과
`out`이나 `inout` 파라미터를 사용할 수 없다는 점이 있습니다.

LLM Inference 결과를 받는 Callback AIDL이기 때문에, Inference 로직이 Callback 완료를 기다리지 않고
쭉 자기 할 일을 할 수 있도록 하기 위해 `oneway interface`로 정의한 것 입니다.

## Stub (Server)
Stub는 AIDL을 구현한 구현체로, 실제 동작을 위한 비즈니스 로직을 포함합니다.<br/>
Stub은 실제로는 Abstract Class 역할로, AIDL 컴파일러가 IPC 관련 메소드 (`onTransact` 등)을
자동으로 추가 정의합니다.

즉, Client의 호출을 받아 실제 동작을 이루는 Server 역할이라고 볼 수 있습니다.

#### MINIVAIService.java
```java
public class MINIVAIService extends IMINIVAIService.Stub {
    private static final String TAG = "MINIVAIService";

    private final LLMEngine mEngine;

    public MINIVAIService() {
        // Constructor implementation
    }

    @Override
    public boolean isReady() {
        return mEngine.isReady();
    }
    
    /// Some more implementation of IMINIVAIService methods...
}
```

그리고, 이 Stub 구현체는 Android Framework의 System server에 등록해주어야 합니다.<br/>
그래야 System이 service를 구동하고, service table에 기록해주어서 Application 단에서 호출할 수 있게 됩니다.
#### android/framework/base/services/java/com/android/server/SystemServer.java
```java
t.traceBegin("StartMINIVAIService");
try {
    ServiceManager.addService("miniv_service", new com.miniv.ai.service.MINIVAIService());
} catch (Throwable e) {
    reportWtf("starting MINIVAIService", e);
}
t.traceEnd();
```

## Proxy (Application Client)
Proxy는 Service 동작을 호출하기 위해 자동으로 생성되는 구성 요소로, Application Client 역할을 담당합니다.
실제로 Proxy 자체를 구현할 필요 없이, 단지 아래와 같은 형식으로 Service를 가져와 Interface로서 호출만 해주면
자동으로 Serialization과 IPC 관련 로직을 시스템에서 처리해줍니다.

```kotlin
val binder = ServiceManager.getService("miniv_service")
val myService = IMINIVAIService.Stub.asInterface(binder)
```
<br/>
<br/>

# Context.getSystemService()
오늘 정리한 AIDL 내용을 정리하며, 기존에 Android Application 개발을 하는 과정에서
`InputMethodService`나 `ConnectivityService`등을 사용할 때 종종 접했던
`Context.getSystemService()`가 떠올라, 어떤 관계가 있는지에 대해서도 알아보았습니다.

`Context`를 통해서 System service를 가져오는 경우에도 마찬가지로 내부적으로는 `ServiceManager`를 호출합니다.
다만, 주로 사용하는 Android의 기본 Service들을 `Context`를 통해서 쉽게 접근할 수 있도록 Wrapping 되어있는 것 입니다.
내부에서는 `SystemServiceRegistry`를 조회하고 Binder를 찾아 반환해주는 복잡하고 귀찮은 일이 일어납니다.<br/>
이로써 Application 개발자가 복잡한 Android OS의 사정을 꼭 알지 않아도 쉽게 기능을 구현할 수 있는 것 입니다.

MINI-V 프로젝트에서 정의한 `miniv_service`처럼 커스텀된 Service는 Android SystemService로 등록되어있지
않기 때문에 이 `Context.getSystemService()`를 사용할 수 없고, 직접 `ServiceManager`를 통해 가져와야 합니다.

물론, 원한다면 직접 만든 서비스를 `SystemServiceRegistry`에 등록해서 `Context`로 쉽게 접근할 수도 있습니다.

## Repositories
[MINI-V Framework](https://github.com/MINI-V-Android/android_frameworks_mini-v)

## Links

[MINI-V Android Intro](https://useful-min.dev/blog/260522-miniv-android-intro)

[MINI-V Android AIDL Service](https://useful-min.dev/blog/260606-miniv-android-aidl-service)

[MINI-V Android Service Test](https://useful-min.dev/blog/260608-miniv-android-service-test)