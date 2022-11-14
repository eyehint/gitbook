---
description: 본인 계정에 등록된 기기 목록 조회하기
---

# 사용자 기기 목록 조회하기

## GET /home/devices

ThinQ 서버에 등록된 사용자의 기기 목록을 조회합니다.

{% hint style="info" %}
[post-account.md](post-account.md "mention")에서 등록된 ThinQ 계정에 대한 정보가 조회됩니다.
{% endhint %}

#### Request

> **URL** : http://{device\_ip}:8951**/home/devices**
>
> **METHOD** : <mark style="color:blue;">**GET**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * None

#### **Response**

> **Type** : List

#### Response Example

```json
[
    {
        "alias": "DAMDA 허브",
        "countryCode": "KR",
        "deviceId": "4262dc0f-8b07-4d43-8974-30b274e8e3ab",
        "deviceState": "D",
        "deviceType": "9001",
        "drServiceYn": "N",
        "guardTimeInterval": null,
        "homeId": "166321876998347325",
        "key": "",
        ...
    },
    {
        "alias": "DAMDA 제품5",
        "countryCode": "KR",
        "deviceId": "ae58c77e-4554-448a-aa8c-8ee776ea6ff5",
        "deviceState": "D",
        "deviceType": "9001",
        "drServiceYn": "N",
        "guardTimeInterval": null,
        "homeId": "166321876998347325",
        "key": "",
        "modelName": "DAMDA_9001",
        "monitoringInterval": null,
        "owner": "KR2209026557161",
        "parentId": "",
        "registeredAt": "2022-11-01T08:03:56.420757+00:00",
        ...
    }
]
```
