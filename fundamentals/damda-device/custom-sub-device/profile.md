# Profile

Profile은 특정 기기 타입이 어떤 capability를 가지는지, 그리고 기기와 연결을 하기 위해서는 어떤 정보가 필요한지(preferences)를 정의합니다.

## Template

{% hint style="warning" %}
Profile 파일명 규칙은 기기의 기능을 정의한 python 코드의 파일명과 반드시 동일해야헙니다.
{% endhint %}

```json
{
    "deviceType": [기기 타입명. camelCase로 정의 (type=string)],
    "name": [식별을 위한 profile의 이름 (type="string")],
    "components": [
        {
            "label": [component를 구분할 alias (type=string)],
            "id": [component id (type="string")],
            "capabilities": [
                {
                    "id": [연결할 capability의 id (type=string)],
                    "version": [연결할 capability의 version (type=int)]
                }
            ]
        }
    ],
    "status": "DEVELOPMENT",
    "preferences": [
        {
            "title": [preference 입력 UI에서 참고할 title (type=string)],
            "name": [preference의 alias (type=string)],
            "description": [preference description (type=string)],
            "required": true,
            "type": ["string","integer" (type=string)]
        }
    ]
}
```

* 생략 가능이라고 적혀있지 않은 요소는 모두 필수로 들어가야합니다
* <mark style="color:red;">**deviceType은 반드시 camelCase**</mark>**로 작성**되야합니다. 이 타입명은, functions의 파일명으로 사용됩니다
* preferences 서브기기 등록 시 필요한 정보입니다. 서브 기기 등록과정에서 사용자에게 preferences에 정의된 값들을 입력받게됩니다.

## Profile Example

<details>

<summary>webOSTV Profile </summary>

파일 이름: webOSTV.json

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

</details>

<details>

<summary>sensorLight Profile</summary>

파일 이름: sensorLight.json

```
{
    "deviceType": "sensorLight",
    "name": "sensor_Light",
    "components": [
        {
            "label": "main",
            "id": "main",
            "capabilities": [
                {
                    "id": "sensorLight",
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
            "description": "IP address of simulator",
            "required": true,
            "type": "string"
        },{
            "title": "Port",
            "name": "port",
            "description": "port of simulator",
            "required": true,
            "type": "integer"
        },
        {
            "title": "Device serial",
            "name": "deviceSerial",
            "description": "Identifier of the sensor",
            "required": true,
            "type": "string"
        }
    ]
}
```

</details>
