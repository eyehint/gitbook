# EMP Access Token 발급

※ EMP(Enterprise Membership Platform) : LG전자 회원 플랫폼을 의미합니다

### POST {Base\_URL}/token

| Description    | ThinQ API에 사용되는 회원 계정의 Access Token을 발급하기 위한 API입니다. ID/Password 및 Refresh Token 방식을 지원하며, 현재 LG Account만 지원됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                               |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- |
| Parameters     | <p>Header Parameters : Authorization을 제외한 공통 Headers를 사용합니다.</p><h4>Body Parameters</h4><table><thead><tr><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>grant_type</td><td>string</td><td>[ password, refresh_token ]</td></tr><tr><td>id</td><td>string</td><td>LG Account ID (password grant type시 필수)</td></tr><tr><td>pasword</td><td>string</td><td>LG Account Password (password grant type시 필수)</td></tr><tr><td>refresh_token</td><td>string</td><td>Refresh Token일 시 필수</td></tr></tbody></table>                                                   |                                               |
| Name           | Type                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Description                                   |
| grant\_type    | string                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | \[ password, refresh\_token ]                 |
| id             | string                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | LG Account ID (password grant type시 필수)       |
| pasword        | string                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | LG Account Password (password grant type시 필수) |
| refresh\_token | string                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Refresh Token일 시 필수                           |
| Result         | <h4>성공</h4><ul><li>Password 방식 : Access Token, Refresh Token, Expired time(Sec.) 반환</li><li>Refresh Token 방식 : Access Token, Expired time(Sec.) 반환</li></ul><h4>실패</h4><p>아래 정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다.</p><table><thead><tr><th>Error Code</th><th>Error Message</th><th>Description</th></tr></thead><tbody><tr><td>412</td><td>required grant_type</td><td>파라미터가 누락됨<br>- grant_type</td></tr><tr><td>412</td><td>required refresh_token</td><td>요청 파라미터가 누락됨<br>- refresh_token</td></tr><tr><td>500</td><td>Login Error</td><td>요청 정보에 오류가 있는 경우</td></tr></tbody></table> |                                               |
| Error Code     | Error Message                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Description                                   |
| 412            | required grant\_type                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | <p>파라미터가 누락됨<br>- grant_type</p>              |
| 412            | required refresh\_token                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | <p>요청 파라미터가 누락됨<br>- refresh_token</p>        |
| 500            | Login Error                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 요청 정보에 오류가 있는 경우                              |

### Request

#### password 방식

```
         ## Header
{
    "x-country-code": "KR",
    "x-message-id": "0123456789012345678912",
}

## Body
{
  "grant_type": "password",
  "id": "abc@mailaddr.com"
  "password": "password"
}
       
```

#### refresh token 방식

```
         ## Header
{
    "x-country-code": "KR",
    "x-message-id": "0123456789012345678912",
}

## Body
{
  "grant_type": "refresh_token",
  "refresh_token": "abcdeqjioeqoiejoqadmaomdkdlkj"
}
       
```

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
