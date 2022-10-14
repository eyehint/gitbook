# 가전 제어

### POST {Base\_URL}/devices/{device-id}

| Description  | LG ThinQ 플랫폼에 등록되어 있는 가전을 제어하기 위한 API입니다.                                                                                                                                                                               |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Precondition | 이 메서드를 사용하기 전, device-id 값을 얻기 위해 반드시 한 번은 디바이스 목록 조회(GET /devices) 메서드를 호출해야 합니다.                                                                                                                                      |
| Parameters   | <p>Header Parameters : 공통 Headers를 사용합니다.<br>Body Parameters : 디바이스별로 다른 파라미터를 가집니다.<a href="https://developer.damda.lge.com/docs/thinq/profile">가전 Profile 보기</a></p><pre><code>{
    // Device Command
}</code></pre> |
| Result       | 성공 Status 200 코드와 빈 값이 반환됩니다. 실패 공통 Responses에 정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다.                                                                                                                                      |
