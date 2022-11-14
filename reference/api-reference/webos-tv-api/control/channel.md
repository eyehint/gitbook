# Channel

## GET /webostv/{ip}/control/channels

전체 채널 리스트를 가져옵니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/channels**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다

#### Response

> Type: List
>
> * TV 채널 정보가 리턴됩니다

#### Response Example

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

## GET /webostv/{ip}/control/channel

현재 채널을 가져옵니다.&#x20;

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/channel**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다

#### Response

> Type: Object
>
> * 현재 채널 정보가 리턴됩니다

#### Response Example

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

## POST /webostv/{ip}/channel/up

채널을 한 칸 올립니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/channel/up**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다

#### Response Example

```
{}
```

## POST /webostv/{ip}/channel/down

채널을 한 칸 내립니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/channel/down**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다

#### Response Example

```
{}
```
