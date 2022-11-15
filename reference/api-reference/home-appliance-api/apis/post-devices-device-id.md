# 가전 제어

## POST /devices/{device-id}

LG ThinQ 플랫폼에 등록되어 있는 가전을 제어하기 위한 API입니다.



**Request**

> **URL** : http://{device\_ip}:5010**/devices/{device-id}**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * [공통 Headers](common-headers.md)를 사용합니다.
>
> **Parameter (Path)**
>
> * device-id (String) <mark style="color:red;">\*</mark>: 정보 조회할 기기의 id.  [get-devices.md](get-devices.md "mention")를 통해 받아옵니다.
>
> #### Parameter (Body)
>
> * 디바이스 별로 다른 파라미터를 가집니다. 기기별 자세한 정의는 [가전 Profile](https://developer.damda.lge.com/docs/thinq/profile/washer)을 참고해주세요



#### Response

> Type: Object
>
> * messageId (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * timestamp (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * response (Object) <mark style="color:red;">\*</mark>:&#x20;
>   * 성공: Status 200 코드와 빈 값이 반환됩니다
>   * 실패: [공통 Response](common-response.md)에[ ](common-response.md)정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다.
