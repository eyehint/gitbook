---
description: DAMDA 기기 내부에 등록된 사용자의 Home 정보를 조회합니다.
---

# POST /hub

### (기기가 ThinQ 서버에 등록되어 있지 않은 경우)DAMDA 기기를 서버에 등록하고, 기기에 사용자가 정의한 정보(meta)를 저장합니다.&#x20;

#### Request

> **URL** : http://localhost:8951**/hub**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * home\_id (String) <mark style="color:red;">\*</mark> : 사용자의 기기를 등록할 ThinQ Home ID 값
> * meta (Object) : 사용자가 추가로 저장할 정보

#### **Response**

> **Type** : Object
>
> * device\_id (String)
> * home\_id (String)
> * meta (Object)
> * device\_type (String)
> * model\_name (String)
> * alias\_prefix (String)

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
