---
description: DAMDA 기기 정보 조회하기
---

# 기기 정보 가져오기

## GET /device

ThinQ 서비스에 저장된 DAMDA 기기의 상세 정보를 조회합니다. &#x20;

{% hint style="info" %}
[post-account.md](post-account.md "mention") 진행 후 사용가능합니다.
{% endhint %}

#### Request

> **URL** : http://{device\_ip}:8951**/device**
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

> **Type** : Object

#### Response Example

```json
{
    "alias": "DAMDA 허브2",
    "blackboxYn": "Y",
    "clientDeviceId": "",
    "concurrencyYn": "",
    "countryCode": "KR",
    "deviceCode": "",
    "deviceId": "311860f6-2bcc-46ad-ae31-be481b3f4d67",
    "deviceIdSelfMadeYn": "N",
    "deviceState": "E",
    "deviceType": "9001",
    "drServiceYn": "N",
    "fareTarget": "",
    "fwVer": "",
    "guardTimeInterval": null,
    "homeId": "164903371889065633",
    "key": "",
    "macAddress": "",
    "modelName": "DAMDA_HUB_9001",
    "modelNumber": "",
    "modemFotaStartTime": null,
    "monitoringInterval": null,
    "networkType": "",
    "nlpAlias": "none",
    "owner": "KR2009066177803",
    "parentId": "",
    "registeredAt": "2022-04-15T08:02:07.037545+00:00",
    "remoteControlType": "",
    "roomId": "",
    "sdsGuide": null,
    "sleep": "",
    "softapId": "",
    "softapPass": "",
    "ssid": "",
    "timezoneCode": "Asia/Seoul",
    "webOSUuid": "",
    "webOSVersion": "",
    "homeOrder": -1,
    "newRegYn": "N",
    "order": 0,
    "regDtUtc": "20220415080207117",
    "regDt": "20220415080207117",
    "rejectYn": "N",
    "roomOrder": -1,
    "serviceCode": "SVC202",
    "userNo": "KR2009066177803",
    "snapshot": {
        "metadata": {},
        "online": true
    },
    "meta": {
        "key": "val"
    }
}
```

> ``
