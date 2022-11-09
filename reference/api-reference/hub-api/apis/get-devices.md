# 서브 디바이스 리스트 조회

## GET /devices

등록된 서브디바이스의 목록을 리턴합니다



**Request**

> **URL** : http://{device\_ip}:5003**/devices**
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
> * resultCode (String) <mark style="color:red;">\*</mark>: API 수행 결과 코드 값
> * result (List) <mark style="color:red;">\*</mark> : 등록된 기기 리스트
>   * 각 기기 정보는[ Device](../types/device.md) 타입으로 정의되어 있음

#### Response Example

```

{
    "resultCode": "0000",
    "result": [
        {
            "deviceId": "8f039f38-e217-47fb-843c-3d30e3238e5c",
            "deviceType": "webOSTV",
            "deviceState": {
                "online": false,
                "mainWebOSTVVolume": 3,
                "mainWebOSTVProgramName": "중계방송  국회 대정부 질문 -경제-",
                "mainWebOSTVMuted": false,
                "mainWebOSTVChannelName": "KBS1",
                "mainWebOSTVChannelNumber": "9-1"
            },
            "alias": "회사 TV",
            "registeredAt": 1660149422,
            "preferences": {
                "ip": "192.168.50.77"
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
        },
        {
            "deviceId": "59636f82-0e9b-46cc-92e9-be7fdba0971e",
            "deviceType": "webOSTV",
            "deviceState": {
                "online": false,
                "mainWebOSTVVolume": 5,
                "mainWebOSTVProgramName": "중계방송  국회 대정부 질문 -경제-",
                "mainWebOSTVMuted": false,
                "mainWebOSTVChannelName": "KBS1",
                "mainWebOSTVChannelNumber": "9-1"
            },
            "alias": "거실 TV",
            "registered_at": 1660147916,
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
    ]
}
```

