---
description: DAMDA기기가 hub가 되어 동작합니다. 정의된 sub device를 등록, 제어, 모니터링 할 수 있습니다.
---

# Hub API

## Prerquisites

샘플 컴포넌트 **com.damda.sample.damda-hub**를 배포하여야 합니다.\
damda-hub는 배포에 평균 5분정도 소요됩니다. 네트워크 상태에 따라 더 긴 시간이 소요될 수 있습니다.

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption><p>배포 목록 com.damda.sample.damda-hub 포함</p></figcaption></figure>

## API List

다른 컴포넌트에서도, API를 통해 dmada-hub 컴포넌트와 통신하여 서브 의 정보를 알아오거나 등록, 제어 등을 할 수 있습니다.

#### 서브 디바이스 타입 관련 API

* [지원하는 서브 디바이스 타입 목록](hub-api/apis/get-device-types.md): <mark style="color:purple;">GET</mark> /deviceTypes
* [특정 기기 타입 프로파일 정보](hub-api/apis/get-profiles-device-type.md): <mark style="color:purple;">GET</mark> /profiles/{device\_type}
* [특정 capability 정보](hub-api/apis/get-capabilities-id-version.md): <mark style="color:purple;">GET</mark> <mark style="color:blue;"></mark> /capabilities/{id}/{version}

#### 서브 디바이스 제어 관련 API

* [서브 디바이스 등록](hub-api/apis/post-devices.md): <mark style="color:green;">POST</mark> /devices
* [서브 디바이스 삭제](hub-api/apis/delete-devices-device-id.md): <mark style="color:red;">DLETE</mark> /devices/{device\_id}
* [등록 / 삭제 결과 확인](hub-api/apis/get-progress-register-register-id.md): <mark style="color:purple;">GET</mark> /progress/register/{register\_id}
* [서브 디바이스 리스트 조회](hub-api/apis/get-devices.md): <mark style="color:purple;">GET</mark> /devices
* [서브 디바이스 정보 조회](hub-api/apis/get-devices-device-id.md): <mark style="color:purple;">GET</mark> /devices/{device\_id}
* [서브 디바이스 상태 조회](hub-api/apis/get-devices-device-id-state.md): <mark style="color:purple;">GET</mark> /devices/{device\_id}/state
* [서브 디바이스 제어](hub-api/apis/post-devices-device-id-control.md): <mark style="color:green;">POST</mark> /devices/{device\_id}/control
* [서브 디바이스 제어 결과 확인](hub-api/apis/get-devices-device-id-control.md): <mark style="color:purple;">GET</mark> /devices/{device\_id}/control
* [서브 디바이스 상태 모니터링](hub-api/apis/undefined.md): <mark style="color:orange;">WS</mark> /devices/{device\_id}/state
* [전체 서브 디바이스 상태 모니터링](hub-api/apis/undefined-1.md): <mark style="color:orange;">WS</mark> /devices/state

## Base URL

Base Url은 **{DAMDA 기기 IP}:5003** 입니다.
