---
description: DAMDA기기가 hub가 되어 동작합니다. 정의된 sub device를 등록, 제어, 모니터링 할 수 있습니다.
---

# Hub API

## Prerquisites

샘플 컴포넌트 **com.damda.sample.damda-hub**를 배포하여야 합니다.\
damda-hub는 배포에 평균 5분정도 소요됩니다. 네트워크 상태에 따라 더 긴 시간이 소요될 수 있습니다.

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption><p>배포 목록 com.damda.sample.damda-hub 포함</p></figcaption></figure>

## API List

다른 컴포넌트에서도, API를 통해 dmada-hub 컴포넌트와 통신하여 서브 의 정보를 알아오거나 등록, 제어 등을 할 수 있습니다.

서브  타입 관련

* [지원하는 서브 디바이스 타입 목록](apis/get-device-types.md): <mark style="color:blue;">GET</mark> /deviceTypes
* [특정 기기 타입 프로파일 정보](apis/get-profiles-device-type.md): <mark style="color:blue;">GET</mark> /profiles/{device\_type}
* [특정 capability 정보](apis/get-capabilities-id-version.md): <mark style="color:blue;">GET</mark> /capabilities/{id}/{version}
* 서브 디바이스 등록: POST /devices
* 서브 디바이스 삭제: DLETE /devices/{device\_id}
* 등록 / 삭제 결과 확인: GET /progress/register/{register\_id}
* 서브 디바이스 리스트 조회: GET /devices
* 서브 디바이스 정보 조회: GET /devices/{device\_id}
* 서브 디바이스 상태 조회: GET /devices/{device\_id}/state
* 서브 디바이스 제어: POST /devices/{device\_id}/control
* 서브 디바이스 제어 결과 확인: GET /devices/{device\_id}/control
* 서브 디바이스 상태 모니터링: WS /devices/{device\_id}/state
* 전체 서브 디바이스 상태 모니터링: WS /devices/state

## Base URL

Base Url은 **{DAMDA 기기 IP}:5003** 입니다.
