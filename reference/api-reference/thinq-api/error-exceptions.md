# Error / Exceptions

API 호출시 다음과 같은 Error / Exception이 발생할 수 있습니다.&#x20;

Error 및 Exception 정보는 다음과 같습니다.&#x20;

| Error / Exceptions            | Status Code | Description                                                                              |
| ----------------------------- | ----------- | ---------------------------------------------------------------------------------------- |
| InternalServerError           | 500         | 아래 정의된 에러 이외의 에러는 모두 InternalServerError로 간주                                             |
| BadRequest                    | 400         | 요청 Body나 Headers에 필요한 필드가 없는 경우                                                          |
| AccountException              | 400         | EMP 계정을 설정 (POST /account)하기 전에 EMP 계정이 필요한 API를 호출한 경우                                  |
| HubAlreadyRegisteredException | 400         | 이미 허브 디바이스로 등록되어 있는데 다시 허브 디바이스 등록 (POST /hub)하는 경우                                      |
| HubNotExistException          | 400         | 허브 디바이스 등록 전에 허브를 조회 (GET /hub) 및 삭제 (DELETE /hub)하는 경우                                  |
| SubDeviceRemainedException    | 400         | 허브 디바이스 삭제 시 (DELETE /hub) 서브 디바이스가 남아 있는 경우                                             |
| SubDeviceNotExistException    | 400         | 서브 디바이스 조회 (GET /sub/{device\_id}) 및 삭제 시 (DELETE /sub/{device\_id}) 해당 서브 디바이스가 없는 경우   |
| EMPException                  | 400         | EMP get\_token, check\_token, refresh\_token 시 에러가 발생하는 경우                               |
| ThinQException                | 400         | ThinQ 서버 (common, service server, iot service server)에서 에러가 발생하는 경우 (resultCode != 0000) |
