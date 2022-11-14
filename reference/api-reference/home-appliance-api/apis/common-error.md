# 공통 | Error

HTTP의 응답 코드로 확인할 수 없는 에러는 에러 코드를 통해 에러 발생 원인을 분석할 수 있습니다.&#x20;

## 에러 메시지 구조

API 실행 중 에러가 발생했을 때 아래와 같은 구조로 에러 값을 반환합니다.

| Name      | Type   | Description                      |
| --------- | ------ | -------------------------------- |
| Error     | Object | 발생한 에러에 대한 상세 설명을 제공하는 오브젝트      |
| └ Message | String | 해당 에러에 대한 간략한 설명                 |
| └ Code    | Enum   | 에러 원인을 상세하게 확인하게 위한 Error Code 값 |

## 가전 API 에러 코드

### 규칙

가전 API의 에러 코드는 클라이언트 에러와 서버 에러로 구분됩니다. LG ThinQ 플랫폼에서 사용하는 ThinQ Connect API의 에러코드와 동일합니다.

* 클라이언트에게 에러 원인을 알려주기 위해 사용됩니다
* 서버 문제로 발생하는 에러를 나타내기 위해 사용됩니다.

| Error Code | Description |
| ---------- | ----------- |
| 1000       | 클라이언트 에러    |
| 11xx       | 파라미터        |
| 12xx       | 리소스         |
| 13xx       | 권한          |
| 2000       | 서버에러        |

### 전체 에러 코드 목록

| Error Code | Text                                              | Description                                                               | HTTP Code |
| ---------- | ------------------------------------------------- | ------------------------------------------------------------------------- | --------- |
| 0000       | Unknown error                                     | 정의 되지 않은 에러 (분석해야 하는 에러)                                                  | 500       |
| 1000       | Bad request                                       | 잘못된 요청                                                                    | 400       |
| 1101       | Missing parameters                                | 필수 입력 항목이 누락됨                                                             | 400       |
| 1102       | Unacceptable parameters                           | 허용하지 않는 파라미터들이 입력됨                                                        | 400       |
| 1103       | Invalid token                                     | 토큰 문법이 잘못됨                                                                | 400       |
| 1104       | Invalid message id                                | 메시지 ID의 문법이 잘못됨                                                           | 400       |
| 1201       | Not registered admin                              | 등록된 관리자가 없음                                                               | 404       |
| 1202       | Not registered user                               | 등록된 사용자가 없음                                                               | 404       |
| 1203       | Not registered service                            | 등록된 서비스가 없음                                                               | 404       |
| 1204       | Not subscribed event                              | 구독된 이벤트가 없음                                                               | 404       |
| 1205       | Not registered device                             | 등록된 디바이스가 없음                                                              | 404       |
| 1206       | Not subscribed push                               | 구독된 푸쉬가 없음                                                                | 404       |
| 1207       | Already subscribed push                           | 등록된 푸쉬가 있음 (동일한 푸쉬가 이미 존재함)                                               | 404       |
| 1208       | Not registered service by admin                   | 관리자가 관리하는 서비스가 아님                                                         | 404       |
| 1209       | Not registered user in service                    | 서비스를 사용하는 사용자가 아님                                                         | 404       |
| 1210       | Not registered device in service                  | 서비스가 허용하는 디바이스 아님                                                         | 404       |
| 1211       | Not registered device by user                     | 사용자가 등록한 디바이스가 아님                                                         | 404       |
| 1212       | Not owned device                                  | 사용자가 가지고 있지 않은 디바이스                                                       | 404       |
| 1213       | Not registered device                             | 등록된 디바이스가 없음                                                              | 404       |
| 1214       | Not subscribable device                           | 이벤트 구독을 허용하지 않는 디바이스                                                      | 404       |
| 1216       | Incorrect Header                                  | 헤더에 포함된 값이 올바르지 않음                                                        | 400       |
| 1217       | Already device deleted                            | 해당 디바이스가 삭제되었음                                                            | 400       |
| 1218       | Invalid token                                     | 유효하지 않은 토큰임                                                               | 400       |
| 1219       | Not supported model                               | 지원하지 않는 제품 모델임                                                            | 406       |
| 1220       | Not supported feature                             | 해당 제품 모델에서는 지원하지 않는 기능임                                                   | 406       |
| 1221       | Not supported product                             | 지원하지 않는 임 (해당 서비스 키에 허용된 디바이스 타입이 아님) 디바이스 타입                             | 406       |
| 1222       | Not connected device                              | 디바이스가 네트워크에 연결되어 있지 않음                                                    | 416       |
| 1223       | Invalid status device                             | 전달된 디바이스 상태 값이 유효하지 않음                                                    | 416       |
| 1224       | Invalid device Id                                 | 허용되지 않은 디바이스 Id                                                           | 404       |
| 1301       | Invalid service key                               | 유효하지 않은 서비스 키                                                             | 401       |
| 1302       | Not found token                                   | 만료된 토큰                                                                    | 401       |
| 1303       | Not found user                                    | 토큰이 발급되지 않은 사용자                                                           | 401       |
| 1304       | Not acceptable terms                              | 서비스 약관 미동의                                                                | 401       |
| 1305       | Not allowed api                                   | 허용되지 않은 API                                                               | 401       |
| 1306       | Exceeded API calls API                            | 호출 횟수 초과                                                                  | 401       |
| 1307       | Not supported country                             | 지원하지 않는 국가                                                                | 401       |
| 1308       | No control autdority                              | 디바이스 제어권 없음 (tdinQ App에서 사용중)                                             | 401       |
| 1310       | Not supported domain                              | 제공되지 않은 도메인을 사용한 경우                                                       | 401       |
| 1311       | Bad request format                                | 요청 포맷이 잘못된 경우                                                             | 401       |
| 1312       | Exceeded number of event subscription             | 해당 서비스 키에 설정된 이벤트 등록 기기 수의 제한을 넘음                                         | 400       |
| 2000       | Internal server error                             | 내부 서버 에러                                                                  | 500       |
| 2101       | Not supported model                               | 지원하지 않은 가전 모델                                                             | 503       |
| 2201       | Not provided feature                              | 지원하는 기능이 아님                                                               | 503       |
| 2202       | Not supported product                             | 지원하는 제품군이 아님                                                              | 400       |
| 2203       | Not existent modelJSON                            | ModelJSON이 없음                                                             | 503       |
| 2205       | Invalid device status                             | 디바이스 상태 정보가 정상적으로 전송되지 않았거나, 전송된 정보가 정상적으로 파싱되지 않았을 경우                    | 400       |
| 2207       | Invalid command error                             | 유효하지 않은 제어 명령일 때 (제어 명령에 정의되지 않은 resource, property 가 포함된 경우)             | 400       |
| 2208       | Fail device control                               | 디바이스 제어 실패                                                                | 400       |
| 2209       | Device response delay                             | 디바이스 응답 지연                                                                | 400       |
| 2210       | Retry request                                     | 상태조회 재요청 필요                                                               | 400       |
| 2212       | Syncing ModelJSON                                 | 싱크 중 (에어솔루션 제품)                                                           | 412       |
| 2213       | Retry after deleting device                       | ModelJSON 싱크 실패. 디바이스 삭제 후 재시도 바람 (에어솔루션 제품)                              | 412       |
| 2214       | Fail Request                                      | 요청 실패                                                                     | 400       |
| 2301       | Command not supported in REMOTE OFF               | 지원하는 제어 명령이 없는 디바이스의 경우 (remoteControl이 false일 때)                         | 400       |
| 2302       | Command not supported in {STATE (Exception Code)} | 해당 STATE에서는 해당 제어 명령을 지원하지 않음 예: "Command not supported in HEAT (2302)"   | 400       |
| 2303       | Command not supported in ERROR                    | 디바이스가 에러 상태여서 제어가 불가능한 경우                                                 | 400       |
| 2304       | Command not supported in POWER OFF                | 디바이스 전원이 꺼져있어서 제어가 불가능한 경우                                                | 400       |
| 2305       | Command not supported in {MODE (Exception Code)}  | 해당 MODE에서는 해당 제어 명령을 지원하지 않음 예: "Command not supported in STANDBY (2305)" | 400       |

## &#x20;<a href="#device-li" id="device-li"></a>
