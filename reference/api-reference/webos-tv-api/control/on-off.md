# ON/OFF

## POST /webostv/{ip}/control/turn\_on

TV 전원을 켭니다.

**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/control/turn\_on**
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
> * 빈 값이 리턴됩니다

#### Response Example

```
{}
```
