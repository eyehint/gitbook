# APIs

### Response

#### password 방식

```
         {
    "access_token":
    "7a407a61366e2d930d4414328875b3996911fd5598e34aa50c98762822a3242e2ecc06cf9252514081ddafec48916495",
    "expires_in": "3600",
    "refresh_token": "9397e5d32045b37353d94b8d42057f5e9ad8a210feacc2fb4d28a694d58fe30c42d955c15fa436825364dde96b59a1a0"
}
       
```

#### refresh\_token 방식

```
         {
    "access_token":
    "7a407a61366e2d930d4414328875b3996911fd5598e34aa50c98762822a3242e2ecc06cf9252514081ddafec48916495",
    "expires_in": "3600"
}
       
```

## Event/Push Callback (Websocket) <a href="#callback" id="callback"></a>

### WSS wss://s7vajyybvf.execute-api.ap-northeast-2.amazonaws.com/websocket

| Description   | 이 메서드는 Websoket을 통하여 ThinQ 가전의 Push 및 Evnet 콜백 메시지를 수신하기 위한 API입니다.                                                                                                                                                                                                                                                                                                     |           |                                                                                 |         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | ------------------------------------------------------------------------------- | ------- |
| Parameters    | <h4>Header Parameters</h4><p>: 없음</p><h4>Query Parameters</h4><table><thead><tr><th>Name</th><th>Type</th><th>Required</th><th>Description</th><th>Default</th></tr></thead><tbody><tr><td>access_token</td><td>String</td><td>Mandatory</td><td>LG EMP(Enterprise Membership Platform)에서 사용자 인증을 위해 OAuth 표준에 따라 발급해주는 토큰 값입니다.</td><td>None</td></tr></tbody></table> |           |                                                                                 |         |
| Name          | Type                                                                                                                                                                                                                                                                                                                                                                    | Required  | Description                                                                     | Default |
| access\_token | String                                                                                                                                                                                                                                                                                                                                                                  | Mandatory | LG EMP(Enterprise Membership Platform)에서 사용자 인증을 위해 OAuth 표준에 따라 발급해주는 토큰 값입니다. | None    |
| Result        | <p>이 메서드의 호출 결과는 다음과 같이 2가지 경우(성공, 실패)가 있습니다.</p><h4>성공</h4><p>연결 성공</p><h4>실패</h4><p>실패한 경우, ThinQ Callback Websocket과의 연결이 되지 않습니다.</p>                                                                                                                                                                                                                               |           |                                                                                 |         |

### Request

```
         ## Query Params
WSS wss://s7vajyybvf.execute-api.ap-northeast-2.amazonaws.com/websocket?access_token=5a9a713f51a95c53d781addd1af0dfa4f6e1e7420a8bff3c5198308dac571aa9845832b8d29bbe1f04deec2d35229c6d
       
```

### Response

없음\
