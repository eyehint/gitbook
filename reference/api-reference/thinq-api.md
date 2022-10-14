---
description: ThinQ 서비스와 연동을 위한 API 입니다.
---

# ThinQ API

DAMDA 기기 내에서 **ThinQ 서비스와 연동**을 위해 다음과 같은 API를 제공합니다.&#x20;

* <mark style="color:green;">POST</mark> /account : _Account 정보 등록하기_&#x20;
* <mark style="color:blue;">GET</mark> /home : 본인 계정에 등록된 홈 목록 조회하기
* <mark style="color:green;">POST</mark> /hub : 기기 정보 등록/저장하기
* <mark style="color:blue;">GET</mark> /hub : ThinQ에 등록된 DAMDA 기기 정보 조회하기
* <mark style="color:green;">POST</mark> /hub/control : DAMDA 기기 제어하기 (다른 Component 제어하기)
* <mark style="color:red;">DELETE</mark> /hub : ThinQ 서비스에서 기기 정보 삭제하기
* <mark style="color:red;">DELETE</mark> /clear : DAMDA 기기 초기화 하기 (계정 정보 삭제, 기기 등록 삭제)
* <mark style="color:yellow;">WS</mark> /{component id}/control : component 제어를 위한 web socket API
