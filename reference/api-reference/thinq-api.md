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
* <mark style="color:blue;">GET</mark> http://{device ip}:8951/home/devices : 본인 계정에 등록된 기기목록 조회하기
* <mark style="color:green;">POST</mark> http://{device ip}:8951/device : ThinQ 서버(damda 서버)에 기기 등록하
* <mark style="color:blue;">GET</mark> http://{device ip}:8951/device : DAMDA 기기 정보 조회하기
* <mark style="color:green;">POST</mark> http://{device ip}:8951/device/control : ThinQ에 등록된  다른 기기 제어하기 (일부기기만 제어가능)
* <mark style="color:red;">DELETE</mark> http://{device ip}:8951/delete : ThinQ 서버에서 기기 정보 삭제하기
* <mark style="color:green;">POST</mark> http://{device ip}:8951/monitoring : 기기에서 ThinQ 서버로 정보 전달하기 (for TPA 통신)

<mark style="color:red;"></mark>

<mark style="color:yellow;"></mark>
