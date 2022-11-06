# Command

## POST /webostv/{ip}/command

### Description

SSAP Full Payload로 TV에 요청하는 API입니다.

### Request

TV의 IP 주소가 필요합니다. ([TV 리스트 조회](get-webostv.md))

### Response

TV가 등록된 경우

```
{
    // TV payload
}
```

TV가 등록되지 않는경우

```
{
    "error": "webOS TV is not registered"
}
```

