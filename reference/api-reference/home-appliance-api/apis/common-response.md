# 공통 | Response

## HTTP 응답 코드

### HTTP 표준 응답 코드 규약

가전 API의 응답 코드는 다음과 같은 HTTP 표준 응답 코드 규약에 따라 정의됩니다.

| HTTP Response Code | Description             |
| ------------------ | ----------------------- |
| 2xx                | 성공                      |
| 4xx                | 에러 (클라이언트에서 요청이 잘못된 경우) |
| 5xx                | 에러 (서버에서 오류가 발생한 경우)    |

### 가전 API에서 사용하는 HTTP 응답코드

&#x20;LG ThinQ 플랫폼에서 사용하는 ThinQ Connect API 응답 코드와 동일합니다. 매 요청마다 다음 중 적절한 응답 코드를 반환합니다.

| HTTP Response Code | Text Message          | Description       |
| ------------------ | --------------------- | ----------------- |
| 200                | OK                    | 정상 응답             |
| 400                | Bad request           | 잘못된 요청임           |
| 401                | Unauthorized          | 권한이 없음            |
| 404                | Not found             | 요청받은 리소스를 찾을 수 없음 |
| 500                | Internal server error | 서버 에러임            |
| 501                | Not implemented       | 아직 구현되지 않음        |
| 503                | Service unavailable   | 사용할 수 없는 서비스임     |

## 응답 메시지

### 공통 메시지

| Name      | Type   | Description                                                                |
| --------- | ------ | -------------------------------------------------------------------------- |
| Messageid | String | 요청 시 헤더에 포함된 X-Message-ID 값입니다. 이 값을 응답 메시지에 포함시켜서 문제가 있을 때 확인할 수 있도록 합니다. |
| Timestamp | String | 요청이 들어왔을 때의 시간을 의미하며 ISO 8601 Format을 따릅니다.                                |

#### 예시

```
{
    "messageId": "fNvdZ1brTn-wWKUlWGoSVw",
    "timestamp": "2019-06-25T04:52:18.370732"
}
      
```

### 에러 메시지

API 실행 중 에러가 발생했을 때, 아래 표와 같은 구조로 에러 값을 반환합니다.

| Name      | Type   | Description                 |
| --------- | ------ | --------------------------- |
| Error     | Object | 발생한 에러에 대한 상세 설명을 제공하는 오브젝트 |
| └ Message | String | 해당 에러에 대한 간략한 설명            |

## &#x20;<a href="#common-err" id="common-err"></a>
