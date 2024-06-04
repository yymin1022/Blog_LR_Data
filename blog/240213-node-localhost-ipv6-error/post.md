안녕하세요!<br>
대학생 1인개발자 LR입니다!

오늘도 간단한 개발 삽질 이야기입니다.

최근 진행중인 Next.JS 기반의 웹 프로젝트에서, Axios를 활용해 `localhost:3001`에 요청을 보내려고 하니
아래와 같은 요상한 에러가 나면서 요청이 정상적으로 이루어지지 않더라고요.

```
cause: Error: connect ECONNREFUSED ::1:3001
  at TCPConnectWrap.afterConnect [as oncomplete] (node:net:1555:16)
  at TCPConnectWrap.callbackTrampoline (node:internal/async_hooks:130:17) {
    errno: -61,
    code: 'ECONNREFUSED',
    syscall: 'connect',
    address: '::1',
    port: 3001
}
```

분명 저는 `localhost:3001`에 요청을 보냈는데, 로그를 확인해보면 `::1:3001`로 요청이 보내지고 있습니다.

왜그런고 하고 한참 구글링을 한 뒤에 이유를 확인하고 해결할 수 있었습니다.

Node.JS 17버전 이후부터는 IPv4보다 IPv6가 우선적으로 적용되도록 변경이 있었는데요,<br>
바로 이때문에 `localhost`가 Node.JS의 DNS 설정을 통해 IPv6의 `::1` 주소로 변경이 된 것이었습니다.

이를 다시 원래 우리의 의도대로 `127.0.0.1`에 요청이 가도록 하기 위해서는 아래 두 구문을 추가해주시면 됩니다.

```typescript
import { setDefaultResultOrder } from "dns";
setDefaultResultOrder("ipv4first");
```

해당 구문이 1회 실행된 이후부터는 의도한대로 IPv4가 우선적으로 적용되어 동작하는 것을 확인해보실 수 있습니다.

감사합니다!