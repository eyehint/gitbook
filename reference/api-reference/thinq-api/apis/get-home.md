---
description: 본인 계정에 등록된 홈 목록 조회하기
---

# 사용자 홈 목록 조회하기

## GET /home

사용자의 ThinQ 서비스 Home 정보를 조회합니다.

{% hint style="info" %}
[post-account.md](post-account.md "mention")에서 등록된 ThinQ 계정에 대한 정보가 조회됩니다.
{% endhint %}

#### Request

> **URL** : http://{device\_ip}:8951**/home**
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
        "homeId": "164903371889065633",
        "homeName": "damda 홈",
        "homeOrder": -1,
        "regDtUtc": "20220404005522",
        "lastUseDt": "20220414140037",
        "sharedYn": "N",
        "bgImage": "62",
        "bgImageUrl": "",
        "startColor": "#ECECEC",
        "centerColor": "",
        "endColor": "",
        "area": "3430109",
        "latitude": "37.4698659",
        "longitude": "127.0266905",
        "localizedAddress": "2330442##양재1동",
        "newHomeYn": "N",
        "atHomeYn": "N",
        "concurrency2": "Y"
    }
]
```
