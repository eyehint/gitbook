---
description: DAMDA 기기와 ThinQ 서비스의 연동을 위한 API 입니다.
---

# ThinQ API

## Prerquisites

DAMDA가 설치 후, 별도로 설정할 것이 없습니다. DAMDA 기기에서는 기기와 ThinQ 서비스간의 연동을 위해 **ThinQ 연동 서비스(ThinQ Agent)가 실행**되고 있습니다.&#x20;

## API List

API 호출을 통하여 기기를 ThinQ 서비스와 연동 시킬 수 있습니다.&#x20;

ThinQ 연동 서비스는 Http 및 websocket 기반의 REST API를 제공합니다.

#### ThinQ 계정 등록하기를 통해 DAMDA 기기에 ThinQ 계정을 등록합니다.

* [ThinQ 계정 등록하기](thinq-api/apis/post-account.md): __ <mark style="color:green;">POST</mark> http://{device ip}:8951/account

#### 아래 API들은 계정을 등록한 이후 사용할 수 있습니다.

* [사용자 홈 목록 조회하기](thinq-api/apis/get-home.md): <mark style="color:purple;">GET</mark> http://{device ip}:8951/home&#x20;
* [사용자 기기목록 조회하기](thinq-api/apis/get-home-devices.md): <mark style="color:purple;">GET</mark> http://{device ip}:8951/home/devices&#x20;
* [ThinQ 서버(damda 서버)에 기기 등록하기](thinq-api/apis/post-device.md): <mark style="color:green;">POST</mark> http://{device ip}:8951/device
* [DAMDA 기기 정보 가져오기](thinq-api/apis/get-device.md): <mark style="color:purple;">GET</mark> http://{device ip}:8951/device
* [ThinQ에 등록된  다른 기기 제어하기 (일부기기만 제어가능)](thinq-api/apis/post-device-control.md): <mark style="color:green;">POST</mark> http://{device ip}:8951/device/control&#x20;
* [ThinQ 서버에서 기기 삭제하기](thinq-api/apis/delete-device.md): <mark style="color:red;">DELETE</mark> http://{device ip}:8951/delete
* [기기에서 ThinQ 서버로 정보 전달하기 (for TPA 통신)](thinq-api/apis/post-monitoring.md): <mark style="color:green;">POST</mark> http://{device ip}:8951/monitoring&#x20;

## Base URL

Base Url은 **{DAMDA 기기 IP}:8951** 입니다.
