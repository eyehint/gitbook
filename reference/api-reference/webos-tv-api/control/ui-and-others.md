# UI 및 기타

## POST /webostv/{ip}/control/toast

TV 화면에 Toast 메시지를 띄웁니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/toast**
>
> **METHOD** : <mark style="color:red;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다
>
> #### Parameter (Body)
>
> * message (String) <mark style="color:red;">\*</mark>: Toast를 띄울 메세지 내용

#### Request Example

```
{
    "message": "안녕하세요!"
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다



## POST /webostv/{ip}/control/alert/youtube

Alert창을 띄워 유튜브 영상을 실행합니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/alert/youtube**
>
> **METHOD** : <mark style="color:red;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다
>
> #### Parameter (Body)
>
> * message (String) <mark style="color:red;">\*</mark>: Toast를 띄울 메세지 내용

#### Request Example

```
{
    "title": "[유튜브] 골드 피즈의 평범한 하루",
    "message": "추천영상입니다. 유튜브 앱에서 시청할까요?",
    "code": "v=96afkL4NXqI"
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다



## GET /webostv/{ip}/control/capture

TV화면을 캡쳐합니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/capture**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")

#### Response

> Type: Object
>
> * returnValue (Boolean) <mark style="color:red;">\*</mark>: 캡처 성공 여부
> * imageUri (String) <mark style="color:red;">\*</mark>: 캡처 이미지를 받을 수 있는 Uri

#### Response Example

```
{
    "returnValue": true,
    "imageUri": "http://192.168.0.41:3000/resources/dbdd8e71478ebdbcac751da54811a185848fed0e/capture.jpg"
}
```



## POST /webostv/{ip}/control/web

TV에서 웹브라우저로 웹사이트를 엽니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/web**
>
> **METHOD** : <mark style="color:red;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](../get-webostv.md "mention")를 통해 얻어옵니다
>
> #### Parameter (Body)
>
> * url (String) <mark style="color:red;">\*</mark>: 브라우저에서 실행할 URL

#### Request Example

```
{
    "url": "https://www.lge.co.kr/"
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다
