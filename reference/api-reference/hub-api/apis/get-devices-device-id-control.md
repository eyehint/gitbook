# 제어 결과 확인

## GET /devices/{device\_id}/control

서브 기기 제어 결과를 확인할 수 있습니다.



**Request**

> **URL** : http://{device\_ip}:5003**/devices/{device\_id}/control**
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
> * result (Object) <mark style="color:red;">\*</mark> : 기기 제어 결과
>   * state (String) <mark style="color:red;">\*</mark> :
>   * result (List) <mark style="color:red;">\*</mark> : 해당 기기의 최근 10개의 제어결과를 포함함
>     * deviceId(String) <mark style="color:red;">\*</mark> : 제어한 기기의 id
>     * result(Object) <mark style="color:red;">\*</mark> : 제어 결과로 기기가 리턴한 값을 보여줌
>     * requestId(String) <mark style="color:red;">\*</mark> : 어떤 제어에 대한 결과인지 확인함
>     * timestamp(String) <mark style="color:red;">\*</mark> : 제어가 발생한 시간을 기록함

#### Response Example

```
{
    "resultCode": "0000",
    "result": {
        "state": "RUNNING",
        "result": [
            {
                "deviceId": "59636f82-0e9b-46cc-92e9-be7fdba0971e",
                "result": {
                    "volume": 20
                },
                "requestId": "6a525465-4def-49ef-9027-10da2c94bfeb",
                "timestamp": 1660294577
            }
        ]
    }
}
```
