# Subscribe

## WS /webostv/{ip}/subscribe

메세지로 구독할 대상을 구분합니다. 채널과 오디오 정보를 구독할 수 있습니다.



**Request**

> **URL** : WS {device\_ip}:5003/devices/{device\_id}/state
>
> **Parameter**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](get-webostv.md "mention")를 통해 얻어옵니다
>
> **Message**&#x20;
>
> 구독할 대상 정보를 보냅니다. String 형태로 보냅니다
>
> * 채널 구독: Channel
> * 오디오 구독: Audio

#### Response

> Type: Object
>
> * 구독한 대상의 정보가 변경될 때마다 값을 받게됩니다.

#### Response Example

{% code title="채널 구독" %}
```
{
    "type":"response",
    "id":"1",
    "payload":{
        "programId":"R109814620",
        "programName":"뉴스브리핑",
        "description":"",
        "startTime":"2021,08,11,04,53,01",
        "endTime":"2021,08,11,06,52,01",
        "localStartTime":"2021,08,11,13,53,01",
        "localEndTime":"2021,08,11,15,52,01",
        "duration":7140,
        "channelId":"1_15_6_1_0_0_0",
        "channelName":"SBS",
        "channelNumber":"6-1",
        "channelMode":"Terrestrial",
        "subscribed":true
    }
}
```
{% endcode %}

{% code title="오디오 구독" %}
```
{
    "type":"response",
    "id":"1",
    "payload":{
        "volumeStatus":{
            "activeStatus":true,
            "adjustVolume":true,
            "maxVolume":100,
            "muteStatus":false,
            "volume":0,
            "mode":"normal",
            "soundOutput":"tv_speaker_headphone"
        },
        "returnValue":true,
        "callerId":"secondscreen.client"
    }
}
```
{% endcode %}
