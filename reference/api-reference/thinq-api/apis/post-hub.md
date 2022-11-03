---
description: ThinQ 서버(DAMDA 서버)에 기기 등록하기
---

# POST /device

### DAMDA 기기를 서버에 등록합니다.&#x20;

#### Request

> **URL** : http://{device\_ip}:8951**/device**
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
> * home\_id (String)
> * meta (Object)

#### Response Example

```json
{
    "home_id": "166321876998347325",
    "meta": {}
}
```
