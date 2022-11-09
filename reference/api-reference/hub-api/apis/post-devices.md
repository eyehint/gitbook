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
> * username (String) <mark style="color:red;">\*</mark> : ThinQ 계정 ID
> * password (String) <mark style="color:red;">\*</mark> : ThinQ 계정 Password

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
> * profile 에 정의된 json 데이터가 리턴됨. 각 정보에 대한 상새한 내용은 [profile.md](../../../../fundamentals/damda-device/custom-sub-device/profile.md "mention")가이드 참조&#x20;

#### Response Example

```
{
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
```

