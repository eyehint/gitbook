# Control

## ON/OFF

### POST /webostv/{ip}/control/turn\_on

#### Description

TV 전원을 켭니다.

#### Request

n/a

#### Response

```
{}
```

## Channel

### GET /webostv/{ip}/control/channels

#### Description

전체 채널 리스트를 가져옵니다.

#### Request

n/a

#### Response

```
[
    {
        "channelNumber": "4-1",
        "majorNumber": 4,
        "minorNumber": 1,
        "chanCode": "UNKNOWN",
        "channelName": "",
        "physicalNumber": 4,
        "sourceIndex": 1,
        "channelType": "Terrestrial Digital TV",
        "channelTypeId": 1,
        "channelMode": "Terrestrial",
        "channelModeId": 0,
        "signalChannelId": "1_4_4_1_0_0_0",
        "descrambled": true,
        "skipped": false,
        "locked": false,
        "fineTuned": false,
        "satelliteLcn": false,
        "shortCut": 0,
        "scrambled": false,
        "serviceType": 2,
        "display": 0,
        "ONID": 0,
        "TSID": 0,
        "SVCID": 0,
        "callSign": "UNKNOWN",
        "ipChanServerUrl": "",
        "payChan": false,
        "IPChannelCode": "UNKNOWN",
        "ipCallNumber": "UNKNOWN",
        "otuFlag": false,
        "adFlag": 0,
        "HDTV": false,
        "Invisible": false,
        "DTV": true,
        "ATV": false,
        "Data": false,
        "Radio": false,
        "Numeric": false,
        "PrimaryCh": true,
        "TV": true,
        "configurationId": 0,
        "satelliteName": " ",
        "Bandwidth": 0,
        "Frequency": 69000,
        "specialService": false,
        "CASystemIDListCount": 0,
        "channelGenreCode": "",
        "channelLogoSize": "",
        "imgUrl": "",
        "imgUrl2": "",
        "favoriteIdxA": 250,
        "favoriteIdxB": 250,
        "favoriteIdxC": 250,
        "favoriteIdxD": 250,
        "favoriteIdxE": 250,
        "favoriteIdxF": 250,
        "favoriteIdxG": 250,
        "favoriteIdxH": 250,
        "waterMarkUrl": "UNKNOWN",
        "ipChanType": "UNKNOWN",
        "ipChanInteractive": false,
        "ipChanCategory": "UNKNOWN",
        "channelNameSortKey": "",
        "ipChanCpId": "UNKNOWN",
        "playerService": "com.webos.service.legacybroadcast",
        "configured": false,
        "adultFlag": 0,
        "isFreeviewPlay": 1,
        "hasBackward": 0,
        "numUnSel": false,
        "channelId": "1_4_4_1_0_0_0",
        "CASystemIDList": {},
        "programId": "1_4_4_1_0_0_0",
        "groupIdList": [
            0
        ],
        "favoriteGroup": [],
        "lastUpdated": ""
    },
    ...
]
```

### GET /webostv/{ip}/control/channel

#### Description

현재 채널을 가져옵니다.&#x20;

#### Request

```
{}
```

#### Response

```
{
    "returnValue": true,
    "channelId": "1_15_6_1_0_0_0",
    "physicalNumber": 15,
    "isScrambled": false,
    "channelTypeName": "Terrestrial Digital TV",
    "isLocked": false,
    "dualChannel": {
        "dualChannelId": null,
        "dualChannelTypeName": null,
        "dualChannelTypeId": 255,
        "dualChannelNumber": null
    },
    "isChannelChanged": false,
    "channelModeName": "Terrestrial",
    "channelNumber": "6-1",
    "isFineTuned": false,
    "channelTypeId": 1,
    "isDescrambled": false,
    "isReplaceChannel": false,
    "isSkipped": false,
    "isHEVCChannel": false,
    "hybridtvType": null,
    "isInteractiveRestrictionChannel": false,
    "isInvisible": false,
    "favoriteGroup": null,
    "channelName": "SBS",
    "channelModeId": 0,
    "signalChannelId": "1_15_6_1_0_0_0"
}
```

### POST /webostv/{ip}/channel/up

#### Description

채널을 한 칸 올립니다.

#### Request

```
{}
```

#### Response

```
{}
```



### POST /webostv/{ip}/channel/down

#### Description

채널을 한 칸 올립니다.

#### Request

<pre><code><strong>{}</strong></code></pre>

#### Response

```
{}
```

## Audio

### GET /webostv/{ip}/control/audio

#### Description

오디오 상태를 가져옵니다.

#### Request

n/a

#### Response

```
{
    "returnValue": true,
    "volumeStatus": {
        "activeStatus": true,
        "adjustVolume": true, "maxVolume": 100, "muteStatus": false,
        "volume": 0, "mode": "normal", "soundOutput": "tv_speaker_headphone"
    },
    "callerId": "com.webos.service.apiadapter",
    "mute": false,
    "volume": 0
}
```

### GET /webostv/{ip}/control/audio/mute

#### Description

음소거 상태를 가져옵니다. (true/false)

#### Request

n/a

#### Response

```
{
    "muted": false,
}
```

### POST /webostv/{ip}/control/audio/mute

#### Description

TV를 음소거합니다. (true:음소거, false: 음소거 해)

#### Request

```
{
    "muted": true/false
}
```

#### Response

```
{
}
```

### POST /webostv/{ip}/control/audio/volume

#### Description

볼륨을 숫자 크기로 설정합니다.

#### Request

```
{
    "volume": 10
}
```

#### Response

```
{
}
```

### POST /webostv/{ip}/control/audio/volume/up

#### Description

볼륨을 한칸 올립니다.

#### Request

```
{}
```

#### Response

```
{}
```

### POST /webostv/{ip}/control/audio/volume/down

#### Description

볼륨을 한칸 립니다.

#### Request

```
{}
```

#### Response

```
{}
```

### GET /webostv/{ip}/control/audio

#### Description

현재 실행중인 앱을 가져옵니다.

### Request

n/a

#### Response

```
{
    "name": "com.webos.app.livetv"
}
```

### POST /webostv/{ip}/control/audio

#### Descriptiond

앱 이름으로 앱을 실행합니다.

### Request

```
"name": "com.webos.app.livetv"
```

#### Response

```
{}
```



### DELETE /webostv/{ip}/control/audio

#### Descriptiond

앱 이름으로 앱을 종료합니다.

#### Request

```
"name": "com.webos.app.livetv"
```

#### Response

```
{}
```

