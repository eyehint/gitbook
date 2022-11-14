# 공통 | Headers

가전 API에서 공통적으로 사용하는 Header 정보입니다.

| Name            | Required  | Description                                                                                                                                                                                                                                               |
| --------------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization   | Mandatory | <ul><li>LG 회원 플랫폼(EMP)에서 사용자 인증을 위해 OAuth 표준에 따라 발급하는 토큰 값입니다.</li><li>이 토큰을 이용하여 LG ThinQ 플랫폼은 어느 사용자의 디바이스 정보를 제공해야 하는지 식별하고, 서비스가 해당 사용자의 디바이스 정보를 이용하도록 승인 받았는지 확인합니다. Bearer {token}</li></ul>                                                       |
| x-country-code  | Fixed     | <p><mark style="color:red;">현재는 한국만 지원합니다. <strong>KR</strong> 로 고정하여 사용합니다.</mark></p><ul><li>서비스를 제공할 국가를 지정할 수 있습니다.</li><li>국가코드 ISO 3166-1 alpha-2를 사용합니다.</li></ul>                                                                                 |
| x-message-id    | Option    | <ul><li>ThinQ 플랫폼으로 요청되는 정보를 추적하기 위한 값 입니다. 특정 API의 흐름을 추적하고 에러 발생 시 원인을 찾을 수 있습니다.</li><li>생성 규칙 - url-safe-base64-no-padding (UUID Version 4)방법으로 생성합니다. 길이는 22자입니다.</li><li>아래 <a href="or-headers.md#x-message-id-python">생성 예시</a>를 참고해주세요</li></ul> |
| x-client-id     | Mandatory | damda console의 **DAMDA Key관리**에서 발급 받은 connect key를 입력합니다.                                                                                                                                                                                                |
| x-client-secret | Mandatory | damda console의 **DAMDA Key관리**에서 발급 받은 connect secret을 입력합니다.                                                                                                                                                                                             |

#### x-message-id 생성 예시 (Python)

```python
import uuid
import base64

messageId = base64.urlsafe_b64encode(uuid.uuid4().bytes)[:-2]
```



### Header Example

```json
{
    "Authorization": "Bearer 5a9a713f51a95c53d781addd1af0dfa4f6e1e7420a8bff3c5198308dac571aa9845832b8d29bbe1f04deec2d35229c6d",
    "x-country-code": "KR",
    "x-message-id": "0123456789012345678912",
    "x-client-id": "abcde12345edfe",
    "x-client-secret": "cbdacbda12345677"
}
```
