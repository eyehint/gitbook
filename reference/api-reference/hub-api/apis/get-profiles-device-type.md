# 기기 profile 가져오기

## GET /profiles/{device\_type}

특정 기기 타입의 profile 정보를 가져옵니다. profile 기기가 사용하는 capability의 정보, 등록시 필요한 정보 등을 작성 파일입니다. profile 대한 자세한 내용은 [profile.md](../../../../fundamentals/damda-device/custom-sub-device/profile.md "mention")을 확인해주세요



**Request**

> **URL** : http://{device\_ip}:5003**/profiles/{device\_type}**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * device\_type (String) <mark style="color:red;">\*</mark>: Profile을 조회하려는 기기 타입명. \
>   허브에서 지원하는 기기타입은 [get-device-types.md](get-device-types.md "mention") 통해서 확인 가능

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
    ]
}

```
