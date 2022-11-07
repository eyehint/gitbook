# 가전 상태 조회

## 가전 상태 조회 <a href="#device-cond" id="device-cond"></a>

### GET {Base\_URL}/devices/{device-id}

| Description                                          | 디바이스의 현재 상태를 조회하기 위한 API입니다.                                                                              |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Precondition                                         | 이 메서드를 사용하기 전, device-id 값을 얻기 위해 반드시 한 번은 디바이스 목록 조회 (GET /devices) 메서드를 호출해야 합니다.                       |
| Parameters                                           | Header Parameters : 공통 Headers를 사용합니다. Body Parameters : None                                             |
| Result                                               | 성공 디바이스의 현재 상태가 반환됩니다. 반환값은 가전별 Profile을 기준으로 작성된 JSON 형태로 반환되며, 가전 타입마다 Profile의 구조가 다릅니다. 가전 Profile 보기 |
| 실패 공통 Responses에 정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다. |                                                                                                           |

### Request 예시

```
## Header
{
    "Authorization" : "Bearer 13d6800857e953e58c0a9f0cf4c1c298ecfa3012d1f9486a1925397a1f2a5d13ac6c898c9eaabda9c57ee8e8eca1006a",
    "x-country-code" : "KR",
    "x-message-id" : "0123456789012345678912",
}
```

### Response 예시

```
{
    "messageId": " c2d362a0-dd0f-11e6-a7c7-abfb76e3e664",
    "timestamp": " 1284101485",
    "response": ${Device Status}
}
```
