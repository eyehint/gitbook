# Remote

## POST /webostv/{ip}/remote/{action}

리모컨의 기능별 버튼을 누릅니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/remote/{action}**
>
> **METHOD** : <mark style="color:red;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](get-webostv.md "mention")를 통해 얻어옵니다
> * action (String) <mark style="color:red;">\*</mark>: home, back ok, exit, up, down, left ,right

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다



## POST /webostv/{ip}/remote/number

리모컨의 숫자 버튼을 누릅니다.

#### **Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/remote/number**
>
> **METHOD** : <mark style="color:red;">**POST**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter (Path)**
>
> * ip (String) <mark style="color:red;">\*</mark>: 연결할 TV의 IP 주소. [get-webostv.md](get-webostv.md "mention")를 통해 얻어옵니다

#### Request Example

```
{
    "number": 1
}
```

#### Response

> Type: Object
>
> * 빈 값이 리턴됩니다
