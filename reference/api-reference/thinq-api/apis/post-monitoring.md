---
description: 기기에서 ThinQ 서버로 정보 전달하기 (for TPA 통신)
---

# 기기 정보 전달하기

## POST /monitoring

기기의 다양한 정보를 ThinQ 서버로 저장합니다. 해당 정보는 TPA에서 활용이 가능합니다.&#x20;

{% hint style="info" %}
[post-account.md](post-account.md "mention") 진행 후 사용가능합니다.
{% endhint %}

#### Request

> **URL** : http://{device\_ip}:8951**/monitoring**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * monitoring (Object)

#### Request Example

```
{
    "monitoring" :
    {
        "LED Status":"ON",
        "Device Stauts": "GOOD"
    }
}
```

#### Response

> **Type** : Object

#### Response Example

```json
{}
```

