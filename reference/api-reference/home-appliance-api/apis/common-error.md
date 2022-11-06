# 공통 | Error

HTTP의 응답 코드로 확인할 수 없는 에러는 에러 코드를 통해 에러 발생 원인을 분석할 수 있습니다. 다음은 ThinQ Connect API에서 공통적으로 사용되는 에러 코드입니다.

### 규칙

ThinQ Connect API의 에러 코드는 클라이언트 에러와 서버 에러로 구분됩니다.

* 클라이언트에게 에러 원인을 알려주기 위해 사용됩니다
* 서버 문제로 발생하는 에러를 나타내기 위해 사용됩니다.

| Error Code | Description |
| ---------- | ----------- |
| 1000       | 클라이언트 에러    |
| 11xx       | 파라미터        |
| 12xx       | 리소스         |
| 13xx       | 권한          |
| 2000       | 서버에러        |

### ThinQ Connect API에서 사용하는 에러 코드

#### 에러 코드 전체 리스트 보기 <a href="#errorcodelist" id="errorcodelist"></a>

### 에러 메시지 구조

API 실행 중 에러가 발생했을 때 아래와 같은 구조로 에러 값을 반환합니다.

| Name      | Type   | Description                      |
| --------- | ------ | -------------------------------- |
| Error     | Object | 발생한 에러에 대한 상세 설명을 제공하는 오브젝트      |
| └ Message | String | 해당 에러에 대한 간략한 설명                 |
| └ Code    | Enum   | 에러 원인을 상세하게 확인하게 위한 Error Code 값 |

## &#x20;<a href="#device-li" id="device-li"></a>
