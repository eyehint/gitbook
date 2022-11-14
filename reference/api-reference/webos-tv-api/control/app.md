# App

## GET /webostv/{ip}/control/app

현재 실행중인 앱을 가져옵니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/app**
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
> * name (String) <mark style="color:red;">\*</mark>: 실행중인 앱의 패키지 명

#### Response Example

```
{
    "name": "com.webos.app.livetv"
}
```



## POST /webostv/{ip}/control/app

앱 이름으로 앱을 실행합니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/app**
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
> #### Parameter (Body)
>
> * name (String) <mark style="color:red;">\*</mark>: 실행중인 앱의 패키지 명

#### Request Example

```
{
    "name": "com.webos.app.livetv"
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다



## DELETE /webostv/{ip}/control/app

앱 이름으로 앱을 종료합니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/app**
>
> **METHOD** : <mark style="color:red;">**DELETE**</mark>
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
> * name (String) <mark style="color:red;">\*</mark>: 실행중인 앱의 패키지 명

#### Request Example

```
{
    "name": "com.webos.app.livetv"
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다

