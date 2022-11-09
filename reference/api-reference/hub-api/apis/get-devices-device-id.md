# 서브 디바이스 정보 조회

## GET /devices/{device\_id}

서브 기기 정보를 얻을 수 있습니다



**Request**

> **URL** : http://{device\_ip}:5003**/devices/{device\_id}**
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
> * result (Object) <mark style="color:red;">\*</mark> : 조회한 기기 정보.[ Device](../types/device.md) 타입으로 정의되어 있음

#### Response Example

```
{
    "resultCode": "0000",
    "result": {
        "deviceId": "59636f82-0e9b-46cc-92e9-be7fdba0971e",
        "deviceType": "webOSTV",
        "deviceState": {
                "online": false,
                "mainWebOSTVVolume": 3,
                "mainWebOSTVProgramName": "중계방송  국회 대정부 질문 -경제-",
                "mainWebOSTVMuted": false,
                "mainWebOSTVChannelName": "KBS1",
                "mainWebOSTVChannelNumber": "9-1"
        },
        "alias": "거실 TV",
        "registeredAt": 1660147916,
        "preferences": {
            "ip": "127.0.0.1"
        },
        "profile": {
            "deviceType": "webOSTV",
            "name": "webOS",
            "components": [
                {
                    "label": "main",
                    "id": "main",
                    "capabilities": [
                        {
                            "id": "webOSTV",
                            "version": 1
                        }
                    ]
                }
            ],
            "status": "DEVELOPMENT",
            "preferences": [
                {
                    "title": "IP Address",
                    "name": "ip",
                    "description": "IP address of the webOS TV",
                    "required": true,
                    "type": "string"
                }
            ]
        }
    }
}
```
