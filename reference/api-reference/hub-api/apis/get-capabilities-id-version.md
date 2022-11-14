# Capability 가져오기

## GET /capabilities/{id}/{version}

Capability는 attribute와 command를 정의를 통해, 할 수 있는 기능을 정의해놓은 파일입니다. id와 version 정보를 가지고 capability 파일을 가져올 수 있습니다. 기기가 사용하는 capability의 id와 version은 profile에 작성되어 있습니다. capability에 대한 자세한 내용은 [capability.md](../../../../fundamentals/damda-device/custom-sub-device/capability.md "mention") 확인해주세요



**Request**

> **URL** : http://{device\_ip}:5003**/capabilities/{id}/{version}**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * id (String) <mark style="color:red;">\*</mark>: 가져오고자 하는 capability id
> * version (String) <mark style="color:red;">\*</mark>: 가져오고자 하는 capability version

#### Response

> Type: Object
>
> * capability 에 정의된 json 데이터가 리턴됨. 각 정보에 대한 상새한 내용은 [capability.md](../../../../fundamentals/damda-device/custom-sub-device/capability.md "mention")가이드 참조&#x20;

#### Response Example

```
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
