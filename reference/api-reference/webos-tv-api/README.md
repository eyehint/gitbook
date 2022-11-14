---
description: webOSTV와 연동 하기 위한 API 입니다
---

# webOS TV API

## Prerquisites

퍼블릭 컴포넌트 **com.damda.public.webos-tv-api**를 배포하여야 합니다.

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>배포 목록 com.damda.public.webosp-tv-api 포함 </p></figcaption></figure>

## API List

DAMDA기기와 TV를 연결하고 제어 할 수 있습니다

#### 같은 네트워크 상에 webOSTV 목록을 검색하여 리턴해줍니다

* [TV 리스트 조회](get-webostv.md): <mark style="color:purple;">GET</mark> /webostv

#### 검색한 결과로 받은 TV IP를 이용하여 아래 등록/제어/구독 명령들을 실행할 수 있습니다.

* [TV 등록](post-webostv.md): <mark style="color:purple;">GET</mark> /webostv/{ip}
* [커스텀 제어](custom-ssap-command.md): <mark style="color:green;">POST</mark> <mark style="color:blue;"></mark> /webostv/{ip}/command
* [정의된 command 를 통한 제어](control/): <mark style="color:green;">POST</mark> /webostv/{ip}/control/\*
* [리모컨 제어](remote.md): <mark style="color:green;">POST</mark> /webostv/{ip}/remote/\*
* [상태 변화 구독](subscribe.md): <mark style="color:orange;">WS</mark> /webostv/{ip}/subscribe

## Base URL

Base Url은 **{DAMDA 기기 IP}:5011** 입니다.

## 공통 Response

### Error

TV가 등록되지 않은 경우 (Status: 412 Precondition Failed)

```
{
    "error": "WebOS TV is not registered"
}
```
