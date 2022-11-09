# Device

등록된 기기의 정보를 나타냅니다

{% code title="JSON representation" %}
```
{
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
```
{% endcode %}

| Key          | Type   | Description                                                                                                              |
| ------------ | ------ | ------------------------------------------------------------------------------------------------------------------------ |
| deviceId     | String | 허브에 저장된 기기 ID                                                                                                            |
| deviceType   | String | 기기 타입. 가능한 값은 [API 리턴값](../apis/get-device-types.md)을 참고                                                                 |
| deviceState  | Object | 기기 상태. 각 기기별로 정의한 key, value 형태의 값을 가짐                                                                                   |
| alias        | String | 기기의 별칭                                                                                                                   |
| registeredAt | String | 기기가 등록된 시간                                                                                                               |
| preferences  | Object | 기기를 등록 할 때 사용한 정보. 기기와 통신하기 위해서도 사용함. 기기가 정의한 key, value 형태로 값을 가짐                                                       |
| profile      | Object | 기기의 특징을 정의한 profile. [Profile](../../../../fundamentals/damda-device/custom-sub-device/profile.md)을 읽어온 데이터가 그대로 포함되어있음. |

