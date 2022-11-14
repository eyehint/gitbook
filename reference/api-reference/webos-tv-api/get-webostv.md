# TV 리스트 조회

## GET /webostv

같은 네트워크에 연결된 webOS TV를 SSDP 프로토콜을 통해 조회합니다.



**Request**

> **URL** : http://{device\_ip}:5011**/webostv**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter**
>
> * None



#### Response

> Type: Object
>
> * webOS TV 정보가 dictionary형태로 리턴됩니다. key는 TV의 ip주소, value는 TV 이름입니다.

#### Response Example

```
{
    "192.168.0.41": "%5bLG%5d%20webOS%20TV%20OLED55GXKNA"
}
```

