---
description: DAMDA기기가 hub가 되어 동작합니다. 정의된 sub device를 등록, 제어, 모니터링 할 수 있습니다.
---

# Hub API

## Prerquisites

샘플 컴포넌트 **com.damda.sample.damda-hub**를 배포하여야 합니다.

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption><p>배포 목록 com.damda.sample.damda-hub 포함</p></figcaption></figure>

## API List

ThinQ 연동 서비스는 Http 및 websocket 기반의 REST API를 제공합니다. (default Port : 8951)

제공되는 API는 다음과 같습니다.&#x20;

* hub에 등록가능한 기기 타입 정보 받아오기: __&#x20;
* 본인 계정에 등록된 홈 목록 조회하기: [<mark style="color:blue;">GET</mark> http://{device ip}:8951/home ](thinq-api/apis/get-home.md)
* 본인 계정에 등록된 기기목록 조회하기: [<mark style="color:blue;">GET</mark> http://{device ip}:8951/home/devices ](thinq-api/apis/get-home-devices.md)
* ThinQ 서버(damda 서버)에 기기 등록하: [<mark style="color:green;">POST</mark> http://{device ip}:8951/device](thinq-api/apis/post-device.md)
* DAMDA 기기 정보 조회하기: [<mark style="color:blue;">GET</mark> http://{device ip}:8951/device](thinq-api/apis/get-device.md)
* ThinQ에 등록된  다른 기기 제어하기 (일부기기만 제어가능): [<mark style="color:green;">POST</mark> http://{device ip}:8951/device/control ](thinq-api/apis/post-device-control.md)
* ThinQ 서버에서 기기 정보 삭제하기: [<mark style="color:red;">DELETE</mark> http://{device ip}:8951/delete](thinq-api/apis/delete-device.md)
* 기기에서 ThinQ 서버로 정보 전달하기 (for TPA 통신): [<mark style="color:green;">POST</mark> http://{device ip}:8951/monitoring](thinq-api/apis/post-monitoring.md)&#x20;

{% swagger method="get" path="" baseUrl="/deviceTypes" summary="사용 가능한 서브기기 타입 리스트" %}
{% swagger-description %}
damda-hub가 인식 가능한 기기 타입들을 리턴합니다.

이 타입들은 /opt/damda/sub-devices 에서 damda-devices 와 user-devices 밑에 정의되어 있습니다.
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resultCode": "0000",
    "result": [
        "motionCamera",
        "matterLight",
        "sensorLight",
        "webOSTV",
        "sensorThermoHygrometer"
    ]
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="/devices" summary="서브 기기 등록" %}
{% swagger-description %}
디바이스 타입 별 profile을 참고하여 요청합니다.

\


등록 가능한 device_type 리스트는 GET /deviceTypes 로 확인할 수 있습니다.
{% endswagger-description %}

{% swagger-parameter in="body" name="alias" required="true" type="String" %}
사용자가 식별 하기 위한 기기의 별칭
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" required="true" type="String" %}
등록하려는 기기의 디바이스 타입

등록가능한 디바이스 타입 리스트 중 선택 (GET /deviceTypes)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="preferences" required="true" type="Dictionary" %}
기기 등록 시 필요한 정보 기기타입의 profile을 확인하여 작성
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="delete" path="" baseUrl="/devices/{device_id}" summary="서브 기기 삭제" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## Base URL

Base Url은 **{DAMDA 기기 IP}:5003** 입니다.
