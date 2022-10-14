---
description: DAMDA 기기 내부에 등록된 사용자의 Home 정보를 조회합니다.
---

# GET /home

#### 기기 사용자의 ThinQ 서비스 서버에 저장된 Home 목록 및 정보를 조회할 수 있습니다. &#x20;

#### Request

> **URL** : http://localhost:8951**/home**
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

> `[`    \
> &#x20;   `{`\
> &#x20;       `"homeId": "164903371889065633",`\
> &#x20;       `"homeName": "damda 홈",`\
> &#x20;       `"homeOrder": -1,`\
> &#x20;       `"regDtUtc": "20220404005522",`\
> &#x20;       `"lastUseDt": "20220414140037",`\
> &#x20;       `"sharedYn": "N",`\
> &#x20;       `"bgImage": "62",`\
> &#x20;       `"bgImageUrl": "",`\
> &#x20;       `"startColor": "#ECECEC",`\
> &#x20;       `"centerColor": "",`\
> &#x20;       `"endColor": "",`\
> &#x20;       `"area": "3430109",`\
> &#x20;       `"latitude": "37.4698659",`\
> &#x20;       `"longitude": "127.0266905",`\
> &#x20;       `"localizedAddress": "2330442##양재1동",`\
> &#x20;       `"newHomeYn": "N",`\
> &#x20;       `"atHomeYn": "N",`\
> &#x20;       `"concurrency2": "Y"`\
> &#x20;   `}`\
> `]`
