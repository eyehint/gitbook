# TV 등록

## POST /webostv/{ip}

TV에 연결을 요청하여 TV에 연결하기 위해서 필요한 정보(client key, mac)을 저장합니다.



**Request**

> **URL** : http://{device\_ip}:5011**/webostv/{ip}**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
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
> * 빈 값이 리턴됩니다

#### Response Example

```
{}
```

{% hint style="warning" %}
API 호출 후 TV 화면에 나타난 Alert 창에서 "예"를 눌러야 등록이 완료 됩니다.

기존에 등록된 TV의 경우 Alert창이 나타나지 않고 바로 등록이 완료됩니다.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (5) (4).png" alt=""><figcaption><p>TV 연결 수락 팝업</p></figcaption></figure>
