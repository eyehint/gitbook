---
description: DAMDA기기가 hub가 되어 동작합니다. 정의된 sub device를 등록, 제어, 모니터링 할 수 있습니다.
---

# Hub API

## Prerquisites

샘플 컴포넌트 **com.damda.sample.damda-hub**를 배포하여야 합니다.\
damda-hub는 배포에 평균 5분정도 소요됩니다. 네트워크 상태에 따라 더 긴 시간이 소요될 수 있습니다.

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption><p>배포 목록 com.damda.sample.damda-hub 포함</p></figcaption></figure>

## API List

{% swagger method="get" path="" baseUrl="/deviceTypes" summary="사용 가능한 서브기기 타입 리스트" %}
{% swagger-description %}
damda-hub가 인식 가능한 기기 타입들을 리턴합니다.

이 타입들은 /opt/damda/sub-devices 에서 damda-devices 와 user-devices 밑에 정의되어 있습니다.
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "resultCode": "0000",
    "result": [
        "motionCamera",
        "matterLight",
        "sensorLight",
        "webOSTV",
        "sensorThermoHygrometer"
    ]
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="/profiles/{device_type}" summary="기기 프로파일 정보 가져오기" %}
{% swagger-description %}
device type의 profile을 가지고 옵니다. Profile에 대한 자세한 설명은 

[가이드](../../fundamentals/damda-device/custom-sub-device/profile.md)

를 참조해주시기 바랍니다.
{% endswagger-description %}

{% swagger-response status="200: OK" description="지원 가능한 타입인 경우  profile 파일을 리턴" %}
```json
{
    "resultCode": "0000",
    "result": {
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
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="" baseUrl="/capabilities/{id}/{version}" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="지원 가능한 타입인 경우  capability 파일을 리턴" %}
```javascript
{
    "id": "webOSTV",
    "version": 1,
    "name": "webOS TV",
    "attributes": {
        "power": {
            "schema": {
                "properties": {
                    "value": {
                        "type": "string",
                        "enum": [
                            "on",
                            "off"
                        ]
                    }
                }
            }
        },
        "volume": {
            "schema": {
                "properties": {
                    "value": {
                        "type": "integer",
                        "minimum": 0,
                        "maximum": 100
                    }
                }
            }
        },
        "muted": {
            "schema": {
                "properties": {
                    "value": {
                        "type": "boolean"
                    }
                }
            }
        },
        "programName": {
            "schema": {
                "properties": {
                    "value": {
                        "type": "string"
                    }
                }
            }
        },
        "channelName": {
            "schema": {
                "properties": {
                    "value": {
                        "type": "string"
                    }
                }
            }
        },
        "channelNumber": {
            "schema": {
                "properties": {
                    "value": {
                        "type": "string"
                    }
                }
            }
        }
    },
    "commands": {
        "powerOn": {
            "name": "power_on",
            "arguments": []
        },
        "powerOff": {
            "name": "power_off",
            "arguments": []
        },
        "setVolume": {
            "name": "set_volume",
            "arguments": [
                {
                    "name": "volume",
                    "schema": {
                        "type": "integer",
                        "minimum": 0,
                        "maximum": 100
                    }
                }
            ]
        },
        "keyMute": {
            "name": "mute",
            "arguments": [
                {
                    "name": "mute",
                    "schema": {
                        "type": "boolean"
                    }
                }
            ]
        },
        "volumeUp": {
            "name": "volume_up",
            "arguments": []
        },
        "volumeDown": {
            "name": "volume_down",
            "arguments": []
        },
        "channelUp": {
            "name": "channel_up",
            "arguments": []
        },
        "channelDown": {
            "name": "channel_down",
            "arguments": []
        },
        "keyHome": {
            "name": "home",
            "arguments": []
        },
        "keyBack": {
            "name": "back",
            "arguments": []
        },
        "keyOk": {
            "name": "ok",
            "arguments": []
        },
        "keyLeft": {
            "name": "left",
            "arguments": []
        },
        "keyRight": {
            "name": "right",
            "arguments": []
        },
        "keyUp": {
            "name": "up",
            "arguments": []
        },
        "keyDown": {
            "name": "down",
            "arguments": []
        },
        "capture": {
            "name": "capture",
            "arguments": [
                {
                    "name": "upload_uri",
                    "schema": {
                        "type": "string"
                    }
                }
            ]
        }
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="/devices" summary="서브 기기 등록" %}
{% swagger-description %}
디바이스 타입 별 profile을 참고하여 요청합니다.

\


등록 가능한 device_type 리스트는 GET /deviceTypes 로 확인할 수 있습니다.
{% endswagger-description %}

{% swagger-parameter in="body" name="alias" required="true" type="String" %}
사용자가 식별 하기 위한 기기의 별칭
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" required="true" type="String" %}
등록하려는 기기의 디바이스 타입

등록가능한 디바이스 타입 리스트 중 선택 (GET /deviceTypes)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="preferences" required="true" type="Dictionary" %}
기기 등록 시 필요한 정보 기기타입의 profile을 확인하여 작성
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="delete" path="" baseUrl="/devices/{device_id}" summary="서브 기기 삭제" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

## Base URL

Base Url은 **{DAMDA 기기 IP}:5003** 입니다.
