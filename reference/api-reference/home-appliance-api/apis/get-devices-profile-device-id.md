# 가전 Profile 조회

## GET /devices/profile/{device-id}

디바이스의 Profile을 조회하기 위한 API입니다. 디바이스 Profile이란, LG 가전의 속성을 가전 타입별로 표준화하여 기술한 정보로, LG ThinQ 플랫폼이 사용하는 디바이스 데이터입니다. 예를 들어, 냉장고에 대한 디바이스 Profile은 온도, 냉동모드, 절전모드, 도어 열림 등 냉장고의 상태를 설명하고 제어하기 위한 속성들을 정의합니다. 이 Profile을 바탕으로 디바이스의 상태를 해석하고 제어 명령을 생성할 수 있습니다.



**Request**

> **URL** : http://{device\_ip}:5010**/devices/profile/{device-id}**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * [공통 Headers](broken-reference)를 사용합니다.
>
> **Parameter (Path)**
>
> * device-id (String) <mark style="color:red;">\*</mark>: 정보 조회할 기기의 id.  [get-devices.md](get-devices.md "mention")를 통해 받아옵니다.

#### Response

> Type: Object
>
> * messageId (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * timestamp (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * response (Object) :&#x20;
>   * 성공: 디바이스의 현재 상태가 반환됩니다. 반환값은 가전별 Profile을 기준으로 작성된 JSON 형태로 반환되며, 가전 타입마다 Profile의 구조가 다릅니다. 자세한 정의는 [가전 Profile](https://developer.damda.lge.com/docs/thinq/profile/washer)을 참고해주세요
>   * 실패: [공통 Response](common-response.md)에[ ](common-response.md)정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다.

#### Response Example

```
{
    "messageId": " c2d362a0-dd0f-11e6-a7c7-abfb76e3e664",
    "timestamp": "1284101485",
    "response": <Device Profile>
}
```
