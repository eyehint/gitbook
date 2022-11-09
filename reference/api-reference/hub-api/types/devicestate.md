# DeviceState

기기 상태 정보를 나타내는 타입입니다. 기기가 표현할 수 있는 상태 정보는 capability에서 attributes에 정의되어 있습니다. 각 attribute가 사용할 수 있는 값의 범위 또한 capability에 정의되어있으니 기기 상태를 확인할 때 참고하시기 바랍니다.\


기기가 어떤 capability를 갖는지는 기기 profile에 정의되어 있습니다.&#x20;

capability와 profile에 대한 정의는 각각 [capability.md](../../../../fundamentals/damda-device/custom-sub-device/capability.md "mention"), [profile.md](../../../../fundamentals/damda-device/custom-sub-device/profile.md "mention") 페이지를 확인해주세요.



상태 정보의 key 값은 <mark style="color:red;">**\[capability의 id].\[기기 타입].\[attribute]**</mark>로 구성됩니다.

예를들어 webOSTV에서 사용하는 state정보는 아래와 같습니다.

#### State Example

```
{
    "main.webOSTV.volume": 21,
    "main.webOSTV.muted": false
}
```

#### Capability Example

참고로 webOSTV의 capability 는 아래와 같이 정의되어 있습니다. capability파일은 언제든지 업데이트 될 수 있으므로, 최신 capability는 damda-hub를 설치한 후 `/opt/damda/sub-devices/damda-devices`에서 확인하시기 바랍니다

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
