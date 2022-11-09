# 서브 디바이스 상태 모니터링

## WS /devices/{device\_id}/state

웹소켓을 통해 서브 기기의 상태값 변화를 지속적으로 받을 수 있습니다.



**Request**

> **URL** : WS /devices/{device\_id}/state
>
> **Parameter (Path)**
>
> * deviceId (String) <mark style="color:red;">\*</mark>: 정보 조회할 기기의 id
>
> **Message**&#x20;
>
> * None

#### Response

> Type: Object
>
> state 가 변경될 때마다 response를 받을 수 있습니다. responses는 [Device State 타입](../types/devicestate.md)으로 표현된 state가 올라옵니다.

#### Response Example

```
{"mainSensorLightTurnOn": "off", "mainSensorLightBrightness": 8}
{"mainSensorLightTurnOn": "off", "mainSensorLightBrightness": 4}
{"mainSensorLightTurnOn": "on", "mainSensorLightBrightness": 4}
{"mainSensorLightTurnOn": "on", "mainSensorLightBrightness": 4}
```
