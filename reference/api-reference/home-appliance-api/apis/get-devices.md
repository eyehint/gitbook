# 가전 목록 조회

## GET /devices

사용자가 LG ThinQ 플랫폼에 등록한 가전 목록을 얻어오기 위한 API입니다. 다른 메서드들을 사용하기 전에 반드시 한 번은 호출되어야 하며, 가전 목록을 한 번 얻어온 후에는 매번 호출할 필요는 없습니다. 이 메서드가 반환해 준 가전 목록에는 디바이스를 식별할 수 있는 device-id가 포함되어 있으며, 이 값으로 대상 디바이스를 지정하여 다른 메서드들을 호출할 수 있습니다.

**Request**

> **URL** : http://{device\_ip}:5010**/devices**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * [공통 Headers](common-headers.md)를 사용합니다.
>
> **Parameter**
>
> * None

#### Response

> Type: Object
>
> * messageId (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * timestamp (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * response (List) : 등록된 기기 리스트를 받아옵니다
>   * deviceld (String) : 디바이스를 식별할 수 있는 ID
>   * deviceInfo (Object) <mark style="color:red;"></mark> : 디바이스에 대한 다음 정보를 담은 오브젝트
>     * deviceType (String) : [디바이스의 가전 타입](../types/device-type.md)
>     * modelName (String) : 디바이스의 모델 이름
>     * alias (String) : 디바이스 닉네임
>     * reportable (Boolean) : 디바이스의 상태 변경 시 발생하는 event에 대해, 서비스가 event를 구독 중인지 여부

#### Response Example

```
{
    "messageId": "0123456789012345678912",
    "timestamp": "2018-02-08T06:23:20.866279",
    "response": [
          {
              "deviceId":
              "0A36FC52-6281-4954-86D5-616A58CEA2C6",
              "deviceInfo": {
                  "deviceType":"DEVICE_REFRIGERATOR",
                  "modelName": "S-TF",
                  "alias": "nickname",
                  "reportable": true
              }
          }
      ]
  }
```
