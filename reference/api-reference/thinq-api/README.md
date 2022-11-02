---
description: DAMDA 기기와 ThinQ 서비스의 연동을 위한 API 입니다.
---

# ThinQ API

DAMDA 기기와 ThinQ 서비스간의 연동을 위해 **ThinQ 연동 서비스(ThinQ Agent)가 실행**되고 있습니다. \
API 호출을 통하여 기기를 ThinQ 서비스와 연동 시킬 수 있습니다.&#x20;

ThinQ 연동 서비스는 Http 및 websocket 기반의 REST API를 제공합니다. (default Port : 8951)

제공되는 API는 다음과 같습니다.&#x20;

* <mark style="color:green;">POST</mark> http://{device ip}:8951/account : _Account 정보 등록하기_&#x20;
* <mark style="color:blue;">GET</mark> http://{device ip}:8951/home : 본인 계정에 등록된 홈 목록 조회하기
* <mark style="color:green;">POST</mark> http://{device ip}:8951/hub : 기기 정보 등록/저장하기
* <mark style="color:blue;">GET</mark> http://{device ip}:8951/hub : ThinQ에 등록된 DAMDA 기기 정보 조회하기
* <mark style="color:green;">POST</mark> http://{device ip}:8951/hub/control : DAMDA 기기 제어하기 (다른 Component 제어하기)
* <mark style="color:red;">DELETE</mark> http://{device ip}:8951/hub : ThinQ 서비스에서 기기 정보 삭제하기
* <mark style="color:red;">DELETE</mark> http://{device ip}:8951/clear : DAMDA 기기 초기화 하기 (계정 정보 삭제, 기기 등록 삭제)
* <mark style="color:yellow;">WS</mark> ws://{device ip}:8951/{component id}/control : component 제어를 위한 web socket API
