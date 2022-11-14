---
description: ThinQ에 등록된  다른 기기 제어하기 (일부기기만 제어가능)
---

# 기기 제어하기

## POST /device/control

ThinQ 서버에 등록된 다른 기기를 제어할 수 있습니다.&#x20;

하나의 기기에 제어명령을 보낼 수도 있고, DAMDA 기기간 제어를 할 수도 있습니다.

{% hint style="info" %}
[post-account.md](post-account.md "mention") 진행 후 사용가능합니다.
{% endhint %}

#### Request&#x20;

> **URL** : http://{device\_ip}:8951**/device/control**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * deviceId (String) \* : 제어할 기기의 device ID를 입력합니다.&#x20;
> * payload (Object) \* : 제어할 기기에서 처리하는 payload

#### **Request Example**

```
{
    "deviceId":"ae58c77e-4554-448a-aa8c-8ee776ea6ff5", 
    "payload" :
        {
        "ctrlKey":"component",
        "command":"ledon",
        "dataSetList":{}
    }
}
```

#### **Response**

> **Type** : Object
>
> * resultCode (string) : 기기제어 결과 코드 값
> * result (Object) : 기기 제어 결과&#x20;
>   * messageId (Sting)
>   * msg (Object) : 기기 제어 결과
>   * msgType (String)&#x20;
>   * timestamp (String)

#### Response Example

```json
{
    "resultCode": "0000",
    "result": {
        "messageId": "py4h2eI1SiieXZKYkUm6uw",
        "msg": {
            "id": "4006a0fd8b3a",
            "result": "success"
        },
        "msgType": "controlResult",
        "timestamp": 1647320135
    }
}
```
