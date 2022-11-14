---
description: ThinQ 가전과 연동하기 위한 가전 API 입니다
---

# 가전 API

## Prerquisites

퍼블릭 컴포넌트 **com.damda.public.thinq-backend-api**를 배포하여야 합니다.

<figure><img src="../../../.gitbook/assets/image (4) (6) (1).png" alt=""><figcaption><p>배포 목록 com.damda.public.thinq-backend-api 포함</p></figcaption></figure>



## API List

ThinQ 내계정에 등록된 LG 가전을 제어할 수 있습니다

#### 가전 목록 조회를 통해 상태 조회 / 제어 등을 하고자하는 기기 id를 가져옵니다.

* [가전 목록 조회](apis/get-devices.md): <mark style="color:purple;">GET</mark> /devices

#### 선택한 기기 id를 이용하여 아래 APi들을 실행할 수 있습니다.

* [가전 상태 조회](apis/get-devices-device-id.md): <mark style="color:purple;">GET</mark> /devices/{device-id}
* [가전 Profile 조회](apis/get-devices-profile-device-id.md): <mark style="color:green;">POST</mark> <mark style="color:blue;"></mark> /devices/profile/{device-id}
* [가전 상태 조회](apis/get-devices-device-id.md): <mark style="color:green;">POST</mark> /webostv/{ip}/control/\*
* [가전 제어](control-device.md): <mark style="color:green;">POST</mark> /devices/{device-id}
* [EMP Access Token 발급](apis/emp-access-token.md): <mark style="color:green;">POST</mark> /token
* [EVENT/Push Callback](apis/event-push-callback-websocket.md): <mark style="color:orange;">wss</mark>://s7vajyybvf.execute-api.ap-northeast-2.amazonaws.com/websocket

## Base URL

Base Url은 **{DAMDA 기기 IP}:5010** 입니다.
