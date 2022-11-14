# 전체 서브 디바이스 상태 모니터링

## &#x20;WS /devices/state

웹소켓을 통해 모든 서브 기기의 상태값 변화를 지속적으로 받을 수 있습니다.



**Request**

> **URL** : WS {device\_ip}:5003/devices/state
>
> **Parameter (Path)**
>
> * None
>
> **Message**&#x20;
>
> * None

#### Response

> Type: Object
>
> state 가 변경될 때마다 rresponse에 모든 기기의 상태값이 올라옵니다. response는 device id를 key로 하고, value는 [Device State 타입](../types/devicestate.md)으로 정의되어있습니다.

#### Response Example

```
{"7a222d83-bc76-4119-bad4-5451054ee67e": {"online": true, "mainWebOSTVVolume": 4, "mainWebOSTVProgramName": "6\uc2dc \ub0b4\uace0\ud5a5", "mainWebOSTVMuted": false, "mainWebOSTVChannelName": "KBS1", "mainWebOSTVChannelNumber": "10-1"}, "subDeviceCount": 2, "allDeviceInfoUpdate": false}
{"7a222d83-bc76-4119-bad4-5451054ee67e": {"online": true, "mainWebOSTVVolume": 4, "mainWebOSTVProgramName": "6\uc2dc \ub0b4\uace0\ud5a5", "mainWebOSTVMuted": false, "mainWebOSTVChannelName": "KBS1", "mainWebOSTVChannelNumber": "9-1"}, "subDeviceCount": 2, "allDeviceInfoUpdate": false}
{"c80fe9d2-b1b8-4fd0-8619-1c2989060b29": {"mainSensorLightTurnOn": "off", "mainSensorLightBrightness": 3}, "subDeviceCount": 2, "allDeviceInfoUpdate": false}
{"c80fe9d2-b1b8-4fd0-8619-1c2989060b29": {"mainSensorLightTurnOn": "off", "mainSensorLightBrightness": 8}, "subDeviceCount": 2, "allDeviceInfoUpdate": false}
```
