---
description: DAMDA 기기 내부에 사용자의 계정을 등록 또는 변경 할 수 있습니다.
---

# POST /account

### EMP 서버에서 access\_token, refresh\_token, user\_no, expired\_time을 전달받아 DAMDA 기기 내부(DB)에 저장합니다.&#x20;

#### Request

> **URL** : http://localhost:8951**/account**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * username (<mark style="color:red;">require</mark>) : ThinQ 계정 ID
> * password (<mark style="color:red;">require</mark>) : ThinQ 계정 Password

#### **Response**

> {}
