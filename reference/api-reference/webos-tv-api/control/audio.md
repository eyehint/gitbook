# Audio

## GET /webostv/{ip}/control/audio

오디오 상태를 가져옵니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/audio**
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
> * 오디오 상태 정보가 리턴됩니다

#### Response Example

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



## GET /webostv/{ip}/control/audio/mute

음소거 상태를 가져옵니다. (true/false)

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/audio/mute**
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
> * 음소거 여부가 리턴됩니다

#### Response Example

```
{
    "muted": false,
}
```



## POST /webostv/{ip}/control/audio/mute

TV를 음소거합니다. (true:음소거, false: 음소거 해제)

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/audio/mute**
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
>
> Parameter (Body)
>
> * muted (Boolean) <mark style="color:red;">\*</mark>: 음소거 여부를 보냅니다.

#### Request Example

```
{
    "muted": true/false
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다

## POST /webostv/{ip}/control/audio/volume

원하는 값으로 볼륨을 설정합니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/audio/volume**
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
>
> Parameter (Body)
>
> * volume (int) <mark style="color:red;">\*</mark>: 설정하려는 volume 값을 보냅니다

#### Request Example

```
{
    "volume": 10
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다



## POST /webostv/{ip}/control/audio/volume/up

볼륨을 한칸 올립니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/audio/volume/up**
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

####

## POST /webostv/{ip}/control/audio/volume/down

볼륨을 한칸 내립니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/audio/volume/down**
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
