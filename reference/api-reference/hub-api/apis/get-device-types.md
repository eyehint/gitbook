# 지원 기기타입 가져오기

## &#x20;GET /deviceTypes

hub에 등록할 수 있는 기기 타입을 가져옵니다.&#x20;

기기 타입은 /opt/damda/sub-devices/ 밑에 정의됩니다. 내가 원하는 기기 타입을 추가하여 hub와 연동할 수 있습니다. 관련 내용은 [custom-sub-device](../../../../fundamentals/damda-device/custom-sub-device/ "mention")참고하세요.

**Request**

> **URL** : http://{device\_ip}:5003**/deviceTypes**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter**
>
> * None

#### Response

> Type: Object
>
> * resultCode (string): API 수행 결과 코드 값
> * result (Object): 지원 기기 타입&#x20;

#### Response Example

```
{
    "resultCode": "0000",
    "result": [
        "sensorLight",
        "motionCamera",
        "webOSTV"
    ]
}
```
