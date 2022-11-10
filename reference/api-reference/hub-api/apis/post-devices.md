# 서브 디바이스 등록하기

## POST /devices

서브 기기를 등록하는 API입니다. 기기 등록 시 필요한 정보는 각 기기의 profile에 [preference라는 key값으로 정의](../../../../fundamentals/damda-device/custom-sub-device/profile.md)되어 있습니다. 기기 등록을 호출 한 후, 등록 절차 완료 여부는 [get-progress-register-register-id.md](get-progress-register-register-id.md "mention")를 사용하여 확인할 수 있습니다.



**Request**

> **URL** : http://{device\_ip}:5003**/devices**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter**
>
> * alias (String) <mark style="color:red;">\*</mark> : 기기를 구분하기 위한 이름
> * deviceType (String) <mark style="color:red;">\*</mark> : 등록할 기기의 타입
> * preferences (Object) <mark style="color:red;">\*</mark> : 기기를 등록하기 위해 필요한 정보. [Profile](../../../../fundamentals/damda-device/custom-sub-device/profile.md)에서 확인 가능

#### Request Example

```
{
    "alias": "거실 TV",
    "deviceType": "webOSTV",
    "preferences":{
        "ip": "127.0.0.1"
    }
}
```

#### Response

> Type: Object
>
> 등록을 위해 만들어진 기기 정보가 리턴됨. 실제로 등록이 완료되었는지는 [등록/삭제 확인 API](get-progress-register-register-id.md)를 호출하여 확인필요.\
> 결과 확인을 위해 response에 포함된 registerId를 사용
>
> * resultCode (String) <mark style="color:red;">\*</mark>: API 수행 결과 코드 값
> * result (Object) <mark style="color:red;">\*</mark> : 등록 진행하는 기기의 정보
>   * device (Object) <mark style="color:red;">\*</mark> : [Device](../types/device.md) 타입으로 정의되어 있음
> * registerId (String) <mark style="color:red;">\*</mark> : 기기 등록이 성공했는지 확인하기 위한 ID

#### Response Example

```
{
    "resultCode": "0000",
    "result": {
        "device": {
            "deviceId": "05f246ad-f6fa-49b4-b90c-d9a908eabe5d",
            "deviceType": "webOSTV",
            "deviceState": {},
            "alias": "거실 TV",
            "registeredAt": 1660262581,
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
        "registerId": "9ff4eae9-41b6-4d8e-b828-723458a5e6db"
    }
}
```

