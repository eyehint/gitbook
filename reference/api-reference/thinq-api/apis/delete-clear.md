---
description: DAMDA 기기 내부에 등록된 사용자의 Home 정보를 조회합니다.
---

# DELETE /clear

### DAMDA 기기를 초기화 합니다.&#x20;

{% hint style="info" %}
초기화 : 서브 기기 전체 삭제, ThinQ 기기 등록 정보 삭제, 사용자 계정 정보 삭
{% endhint %}

#### Request

> **URL** : http://localhost:8951**/clear**
>
> **METHOD** : <mark style="color:red;">**DELETE**</mark>
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
{}
```
