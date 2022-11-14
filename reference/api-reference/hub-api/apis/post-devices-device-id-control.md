# 서브 디바이스 제어

## POST /devices/{device\_id}/control

서브 기기를 제어할 수 있습니다. 가능한 기기 제어 명령은 capability에 작성되어 있습니다.&#x20;

기기가 사용하는 capability 정보는 [기기 정보 조회](get-devices-device-id.md), 혹은 [기기의 profile 조회](get-profiles-device-type.md)를 하여 확인할 수 있습니다.\
response에서 component의 id와 버전을 확인한 후, [capability 가져오기](get-capabilities-id-version.md) API를 사용하여 확인할 수 있습니다. \
Capability에 대한 정의는 [capability.md](../../../../fundamentals/damda-device/custom-sub-device/capability.md "mention")를 확인해주시기 바랍니다.



**Request**

> **URL** : http://{device\_ip}:5003**/devices/{device\_id}/control**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * device\_id (String) <mark style="color:red;">\*</mark>: 제어할 기기의 id
>
> **Parameter (Body)**
>
> * component (String) <mark style="color:red;">\*</mark>: 제어에 사용할 명령어가 정의된 capability의 component
> * capability (String) <mark style="color:red;">\*</mark>: 제어에 사용할 명령어가 정의된 capability id
> * command (String) <mark style="color:red;">\*</mark>: 제어에 사용할 명령어. capability의 commands에 정의 되어있어야 함
> * arguments (object) <mark style="color:red;">\*</mark>: command에서 사용할 arguments를 key, value 형태로 정의함.\
>   capability의 command 정의에 포함되지 않은 argument를 추가로 보내는 경우, 해당 데이터는 무시됨. 만약 필수로 포함되어야하는 argument가 포함되지 않은 경우는 에러 발생

**Request Example**

```
{
    "component": "main",
    "capability": "webOSTV",
    "command": "setVolume",
    "arguments": {
        "volume": 20
     
    }
}
```

#### Response

> Type: Object
>
> * resultCode (String) <mark style="color:red;">\*</mark> : API 수행 결과 코드 값
> * result (Object) <mark style="color:red;">\*</mark> : 기기 제어 요청 결과
>   * requestId (String) <mark style="color:red;">\*</mark> : 제어 요청 결과를 확인하기 위한 id

#### Response Example

```
{
    "resultCode": "0000",
    "result": {
        "requestId": "6a525465-4def-49ef-9027-10da2c94bfeb"
    }
}
```
