# Event/Push Callback (Websocket)

## WSS wss://s7vajyybvf.execute-api.ap-northeast-2.amazonaws.com/websocket

이 메서드는 Websoket을 통하여 ThinQ 가전의 Push 및 Evnet 콜백 메시지를 수신하기 위한 API입니다.

{% hint style="info" %}
정해진 callback 서버를 호출합니다.&#x20;

* BaseUrl: s7vajyybvf.execute-api.ap-northeast-2.amazonaws.com
{% endhint %}



**Request**

> **URL** : WS {device\_ip}:5003/devices/{device\_id}/state
>
> **Parameter (Query)**
>
> * access\_token (String) <mark style="color:red;">\*</mark>: LG EMP(Enterprise Membership Platform)에서 사용자 인증을 위해 OAuth 표준에 따라 발급해주는 토큰 값입니다.
>
> **Message**&#x20;
>
> * None

#### Request Example

```
## Query Params
wss://s7vajyybvf.execute-api.ap-northeast-2.amazonaws.com/websocket?access_token=5a9a713f51a95c53d781addd1af0dfa4f6e1e7420a8bff3c5198308dac571aa9845832b8d29bbe1f04deec2d35229c6d

```

#### Response

> Type: Object
>
> * 성공: 소켓 연결에 성공합니다. 별도의 응답은 없습니다.
> * 실패: ThinQ Callback Websocket과 연결이 되지 않습니다.
