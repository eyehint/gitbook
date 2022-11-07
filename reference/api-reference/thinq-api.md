---
description: DAMDA 기기와 ThinQ 서비스의 연동을 위한 API 입니다.
---

# ThinQ API

## Prerquisites

DAMDA가 설치 후, 별도로 설정할 것이 없습니다. DAMDA 기기에서는 기기와 ThinQ 서비스간의 연동을 위해 **ThinQ 연동 서비스(ThinQ Agent)가 실행**되고 있습니다.&#x20;

## API List

API 호출을 통하여 기기를 ThinQ 서비스와 연동 시킬 수 있습니다.&#x20;

ThinQ 연동 서비스는 Http 및 websocket 기반의 REST API를 제공합니다.\
제공되는 API는 다음과 같습니다.&#x20;

* Account 정보 등록하기 : __ [<mark style="color:green;">POST</mark> http://{device ip}:8951/account](thinq-api/apis/post-account.md)
* 본인 계정에 등록된 홈 목록 조회하기: [<mark style="color:blue;">GET</mark> http://{device ip}:8951/home ](thinq-api/apis/get-home.md)
* 본인 계정에 등록된 기기목록 조회하기: [<mark style="color:blue;">GET</mark> http://{device ip}:8951/home/devices ](thinq-api/apis/get-home-devices.md)
* ThinQ 서버(damda 서버)에 기기 등록하: [<mark style="color:green;">POST</mark> http://{device ip}:8951/device](thinq-api/apis/post-device.md)
* DAMDA 기기 정보 조회하기: [<mark style="color:blue;">GET</mark> http://{device ip}:8951/device](thinq-api/apis/get-device.md)
* ThinQ에 등록된  다른 기기 제어하기 (일부기기만 제어가능): [<mark style="color:green;">POST</mark> http://{device ip}:8951/device/control ](thinq-api/apis/post-device-control.md)
* ThinQ 서버에서 기기 정보 삭제하기: [<mark style="color:red;">DELETE</mark> http://{device ip}:8951/delete](thinq-api/apis/delete-device.md)
* 기기에서 ThinQ 서버로 정보 전달하기 (for TPA 통신): [<mark style="color:green;">POST</mark> http://{device ip}:8951/monitoring](thinq-api/apis/post-monitoring.md)&#x20;

## Base URL

Base Url은 **{DAMDA 기기 IP}:8951** 입니다.
