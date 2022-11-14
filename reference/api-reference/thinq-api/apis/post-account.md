---
description: Account 정보 등록하기
---

# ThinQ 계정 등록하기

## POST /account

DAMDA 기기에 본인의 EMP 계정 정보(ThinQ앱 로그인 정보)를 등록합니다.&#x20;

{% hint style="info" %}
기기 등록을 하기 위해서는 계정 정보가 반드시 필요합니다
{% endhint %}

{% hint style="warning" %}
DAMDA Home을 통해 기기를 등록한 경우에는 생략 가능합니다.
{% endhint %}

#### Request

> **URL** : http://{device\_ip}:8951**/account**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * username (String) <mark style="color:red;">\*</mark> : ThinQ 계정 ID
> * password (String) <mark style="color:red;">\*</mark> : ThinQ 계정 Password

#### **Response**

> **Type** : Object

#### Response Example

```json
{}
```
