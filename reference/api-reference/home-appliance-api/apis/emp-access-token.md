# EMP Access Token 발급

{% hint style="info" %}
EMP(Enterprise Membership Platform) : LG전자 회원 플랫폼을 의미합니다

EMP는 기존 공통헤더에서 쓰던 DAMDA Connect Key가 아닌 DAMDA EMP Key를 발급받아서 입력해야 합니다. [헤더 예제](emp-access-token.md#request-example)를 참고하세요.
{% endhint %}

## POST /token

ThinQ API에 사용되는 회원 계정의 Access Token을 발급하기 위한 API입니다. ID/Password 및 Refresh Token 방식을 지원하며, 현재 LG Account만 지원됩니다.



**Request**

> **URL** : http://{device\_ip}:5010**/token**
>
> **METHOD** : <mark style="color:green;">**POST**</mark>
>
> **Header**&#x20;
>
> * Authorization을 제외한 [공통 Headers](common-headers.md)를 사용합니다.
>
> #### Parameter (Body)
>
> * grant\_type (String) : 어떤 방식으로 로그인할지 나타냅니다. "password" 혹은 "refresh\_token" 을 값으로 사용합니다
> * id (String) : LG Account ID. **grant\_type이 password일 때 필수**입니다.
> * password (String) : LG Account Password. **grant\_type이 password일 때 필수**입니다.
> * refresh\_token (String) : account token 만료 시, 재로그인에 사용될 refresh token 값입니다. **grant\_type이 refresh token일 때 필수**입니다.

#### Request Example

{% code title="password 방식" %}
```
## Header
{
    "x-country-code": "KR",
    "x-message-id": "0123456789012345678912",
    "x-client-id": "abcdeq134566112313",
    "x-client-secret": "vbbgqfefqqeqadaeqeqeq"
}

## Body
{
  "grant_type": "password",
  "id": "abc@mailaddr.com"
  "password": "password"
}
       
```
{% endcode %}

{% code title="refresh token 방식" %}
```
## Header
{
    "x-country-code": "KR",
    "x-message-id": "0123456789012345678912",
    "x-client-id": "abcdeq134566112313",
    "x-client-secret": "vbbgqfefqqeqadaeqeqeq"
}

## Body
{
  "grant_type": "refresh_token",
  "refresh_token": "abcdeqjioeqoiejoqadmaomdkdlkj"
}
```
{% endcode %}



#### Response

> Type: Object
>
> * messageId (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * timestamp (String) <mark style="color:red;">\*</mark>: [공통 Response](common-response.md#undefined-1)를 참고합니다
> * response (Object) :&#x20;
>   * 성공:&#x20;
>     * Password 방식 : Access Token, Refresh Token, Expired time(Sec.) 반환
>     * Refresh Token 방식 : Access Token, Expired time(Sec.) 반환
>   *   실패: 아래 정의된 응답 규약에 따라 에러 코드와 에러 메시지가 반환됩니다.
>
>       | Error Code | Error Message           | Description                            |
>       | ---------- | ----------------------- | -------------------------------------- |
>       | 412        | required grant\_type    | <p>파라미터가 누락됨<br>- grant_type</p>       |
>       | 412        | required refresh\_token | <p>요청 파라미터가 누락됨<br>- refresh_token</p> |
>       | 500        | Login Error             | 요청 정보에 오류가 있는 경우                       |

#### Response Example

{% code title="password 방식" %}
```
{
    "access_token":
    "7a407a61366e2d930d4414328875b3996911fd5598e34aa50c98762822a3242e2ecc06cf9252514081ddafec48916495",
    "expires_in": "3600",
    "refresh_token": "9397e5d32045b37353d94b8d42057f5e9ad8a210feacc2fb4d28a694d58fe30c42d955c15fa436825364dde96b59a1a0"
}
       
```
{% endcode %}

{% code title="refresh_token 방식" %}
```
{
    "access_token":
    "7a407a61366e2d930d4414328875b3996911fd5598e34aa50c98762822a3242e2ecc06cf9252514081ddafec48916495",
    "expires_in": "3600"
}
       
```
{% endcode %}
