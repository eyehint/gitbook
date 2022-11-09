# 서브 디바이스 상태 조회

## GET /devices/{device\_id}/state

기기 상태를 얻을 수 있습니다



**Request**

> **URL** : http://{device\_ip}:5003**/devices/{device\_id}/state**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * deviceId (String) <mark style="color:red;">\*</mark>: 정보 조회할 기기의 id

#### Response

> Type: Object
>
> * resultCode (String) <mark style="color:red;">\*</mark>: API 수행 결과 코드 값
> * result (Object) <mark style="color:red;">\*</mark> : 기기 상태

#### Response Example

```

{
    "resultCode": "0000",
    "result": {
        "main.webOSTV.volume": 21,
        "main.webOSTV.muted": false
    }
}
```
