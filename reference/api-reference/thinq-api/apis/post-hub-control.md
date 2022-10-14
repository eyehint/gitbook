---
description: DAMDA 기기 내부에 등록된 사용자의 Home 정보를 조회합니다.
---

# POST /hub/control

### DAMDA 기기 및 서브기기, Component를 제어합니다.

#### Request

> **URL** : http://localhost:8951**/hub/control**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * message-id (option) : 로깅을 위한 id, 미 입력시 기기 내부에서 자동으로 생성
>
> **Parameter (Body)**
>
> * ctrlKey (String) \* : 제어할 대상 "Hub", "subDevice", "component"&#x20;
> * command (String) \* : 제어 대상에서 동작하기 위해 정의된 command (제어 대상별로 다름)
> * dataSetList (String) :&#x20;
> * componentId (String) \* : 제어할 component의 id \
>   (componentId는 ctrlKey가 "component"일 때만 필수 값으로 요구됩니다. )

#### **Response**

> **Type** : Object
>
> * resultCode (string) : 기기제어 결과 코드 값
> * result (Object) : 기기 제어 결과&#x20;
>   * messageId (Sting)
>   * msg (Object) : 기기 제어 결과 정
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
            "result": "success",
            "type": "HTS000"
        },
        "msgType": "controlResult",
        "timestamp": 1647320135
    }
}
```
