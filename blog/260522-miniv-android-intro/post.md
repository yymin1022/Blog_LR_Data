---
title: "Project MINI-V: Intro"
date: "May 22. 2026"
tag: ["Android","LLaMA","OS"]
isPinned: true
url: "260522-miniv-android-intro"
---

MINI-V Android 프로젝트는 LLaMA 기반의 AI 서비스를 탑재한
Custom Android 프로젝트입니다.

이번 포스팅에서는 MINI-V Android 프로젝트의 첫 이야기로서
Android 내 설계 구조에 대해 이야기해보려고 합니다.

<br/>

## MINI-V

먼저, MINI-V Android는 Google AOSP에서 한단계 커스터마이징이 더해진
LineageOS를 기반으로 개발합니다.

MINI-V Android에서는 아래 오픈소스 레포지토리를 기반으로 Qualcomm Hexagon NPU에 최적화된 LLaMA 모델을
기본 탑재하고, 이를 통해 On-device AI 채팅 기능과 각종 편의 기능을 제공할 예정입니다.

[htp-ops-lib](https://github.com/haozixu/htp-ops-lib)

[llama.cpp-npu](https://github.com/haozixu/llama.cpp-npu)

<br/>

## System Structure

실제 프로젝트 진행에 앞서, 먼저 Android 시스템 내부에서의 구조를 설계해보았습니다.

먼저, MINI-V AI 서비스는 아래와 같이 총 3개의 Layer로 구성됩니다
- User Application
- AI Service
- Model Inference Daemon

이를 각 Android System Layer에 매칭하면 다음과 같습니다.
- Application Layer
- AI Service -> System Layer
- Model Inference Daemon -> Vendor Layer

따라서, 저희는 총 2명의 팀원이 각자 개발 담당을 분리하여
제가 Application Layer와 System Layer를, 다른 팀원이 Vendor Layer를 개발하기로 하였습니다.

<br/>

## Progress

앞으로 MINI-V Android의 개발을 진행하며, 각 Layer 구현 과정을 포스팅으로 정리해 이곳에 모아둘 예정입니다.

[MINI-V Android GitHub](https://github.com/MINI-V-Android)

[MINI-V Android Intro](https://useful-min.dev/blog/260522-miniv-android-intro)

[MINI-V Android AIDL Service](https://useful-min.dev/blog/260606-miniv-android-aidl-service)

[MINI-V Android Service Test](https://useful-min.dev/blog/260608-miniv-android-service-test)