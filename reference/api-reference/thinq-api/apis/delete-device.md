---
description: ThinQ 서버에서 기기 정보 삭제하기
---

# 기기 삭제하기

## DELETE /device

ThinQ 서버에서 기기 정보를 제거(unregister) 합니다.

{% hint style="info" %}
[post-account.md](post-account.md "mention") 진행 후 사용가능합니다.
{% endhint %}

#### Request

> **URL** : http://{device\_ip}:8951**/device**
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
