# TV 등록

## POST /webostv/{ip}

### Description

TV에 연결을 요청하여 TV에 연결하기 위해서 필요한 정보(client key, mac)을 저장합니다.

### Request

연결할 TV의 IP 주소가 필요합니다. ([TV 리스트 조회](tv.md))

### Response

```
{}
```

API 호출 후 TV 화면에 나타난 Alert 창에서 "예"를 눌러야 등록이 완료 됩니다.

기존에 등록된 TV의 경우 Alert창이 나타나지 않고 바로 등록이 완료됩니다.

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
