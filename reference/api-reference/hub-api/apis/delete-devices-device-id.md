# 서브 디바이스 삭제하기

## DLETE /devices/{device\_id}

서브 기기를 삭제하는 API입니다. 이 API를 호출하면, 허브와 기기간 연결이 끊어져있더라도 허브에서 기기를 삭제합니다. 이 경우 각 기기의 방식에 맞춰 직접 기기를 초기화 해야 합니다.



**Request**

> **URL** : http://{device\_ip}:5003**/devices/{device\_id}**
>
> **METHOD** : <mark style="color:red;">**DELETE**</mark>
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
> 삭제 할 기기 정보가 리턴됨. 실제로 삭제가 완료되었는지는 [등록/삭제 확인 API](get-progress-register-register-id.md)를 호출하여 확인필요.\
> 결과 확인을 위해 response에 포함된 registerId를 사용
>
> * resultCode (String) <mark style="color:red;">\*</mark>: API 수행 결과 코드 값
> * result (Object) <mark style="color:red;">\*</mark> : 삭제 기기의 정보
>   * device (Object) <mark style="color:red;">\*</mark> : [Device](../types/device.md) 타입으로 정의되어 있음
> * registerId (String) <mark style="color:red;">\*</mark> : 기기 삭제가 성공했는지 확인하기 위한 ID

#### Response Example

```
{
    "resultCode": "0000",
    "result": {
        "device": {
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
        },
        "registerId": "27caecee-e3c3-45b0-b435-4cdd2c635119"
    }
}
```
