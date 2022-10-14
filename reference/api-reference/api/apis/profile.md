# 가전 Profile 조회

## 가전 Profile 조회 <a href="#device-pro" id="device-pro"></a>

### GET {Base\_URL}/devices/profile/{device-id}

| Description  | 디바이스의 Profile을 조회하기 위한 API입니다. 디바이스 Profile이란, LG 가전의 속성을 가전 타입별로 표준화하여 기술한 정보로, LG ThinQ 플랫폼이 사용하는 디바이스 데이터입니다. 예를 들어, 냉장고에 대한 디바이스 Profile은 온도, 냉동모드, 절전모드, 도어 열림 등 냉장고의 상태를 설명하고 제어하기 위한 속성들을 정의합니다. 이 Profile을 바탕으로 디바이스의 상태를 해석하고 제어 명령을 생성할 수 있습니다. |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Precondition | 이 메서드를 사용하기 전, device-id 값을 얻기 위해 반드시 한 번은 디바이스 목록 조회(GET /devices) 메서드를 호출해야 합니다.                                                                                                                                                                        |
| Parameters   | <p>Header Parameters : 공통 Headers를 사용합니다.<br>Body Parameters : None</p>                                                                                                                                                                                   |
| Result       | <h4>성공</h4><p>디바이스의 가전 타입에 따라 디바이스 Profile이 JSON 형태로 반환됩니다. <a href="https://developer.damda.lge.com/docs/thinq/profile">가전 Profile 보기</a></p><h4>실패</h4><p>공통 Responses에 정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다.</p>                                         |

### Request 예시

```
## Header
{
    "authorization": "Bearer a6586272fc390566850bc5a837d32872f0c794498f651b5174244451700e2ea00ddb8dcc96902ea469aa765e589a221d",
    "x-country-code": "KR",
    "x-message-id": "0123456789012345678912",
}
```

### Response 예시

```
{
    "messageId": " c2d362a0-dd0f-11e6-a7c7-abfb76e3e664",
    "timestamp": "1284101485",
    "response": <Device Profile>
}
```
