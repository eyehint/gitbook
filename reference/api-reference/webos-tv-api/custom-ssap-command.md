# Custom SSAP Command

## POST /webostv/{ip}/command

SSAP Full Payload로 TV에 요청하는 API입니다.



**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}/command**
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



#### Response

> Type: Object
>
> * TV가 등록된 경우: 제어 명령이 실행된 후 TV 에서 보낸 응답이 리턴됩니다
> * TV가 등록되지 않은 경우, 에러 응답이 리턴됩니다

#### Response Example

{% code title="TV가 등록된 경우" %}
```
{
    // TV payload
}
```
{% endcode %}

{% code title="TV가 등록되지 않는경우" %}
```
{
    "error": "webOS TV is not registered"
}
```
{% endcode %}

