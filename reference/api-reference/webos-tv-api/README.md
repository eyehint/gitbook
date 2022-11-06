# webOS TV API

## 준비사항

퍼블릭 컴포넌트 **com.damda.public.webos-tv-api**를 배포하여야 합니다.

<figure><img src="../../../.gitbook/assets/image (12) (4).png" alt=""><figcaption></figcaption></figure>

## Base URL

Base Url은 {DAMDA 기기 api}:5011 입니다.

|     |                       |                                                                                                                                                                                                |
| --- | --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| API | http://127.0.0.1:5011 | <p><a href="get-webostv.md">TV 리스트 조회<br></a><a href="post-webostv.md">TV 등록<br></a><a href="command.md">Command</a><br><a href="control.md">Control</a><br><a href="remote.md">Remote</a></p> |
| WS  | ws://127.0.0.1:5011   | [Subscribe](subscribe.md)                                                                                                                                                                      |



## Parameter

모든 webOS TV API에서 동일하게 사용되는 TV IP 파라메터 입니다.

| Name | Type   | Description | Required |
| ---- | ------ | ----------- | -------- |
| IP   | String | 연결할 TV IP 주 | Yes      |

## Response

### Error

TV가 등록되지 않은 경우 (Status: 412 Precondition Failed)

```
{
    "error": "WebOS TV is not registered"
}
```
