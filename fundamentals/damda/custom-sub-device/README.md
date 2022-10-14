# Custom Sub Device

DAMDA 에서는 새로운 기기 타입을 추가하여 연동 및 제어를 해볼 수 있습니다.

DAMDA에 새로운 서브 디바이스를 추가하고 싶을 때는 아래 3가지를 만들어야 합니다.

1. [Capability 생성](capability.md)
2. [Profile 생성](profile.md)
3. [기기 코드 추가](functions.md)

작성한 파일들은 경로에 맞춰 DAMDA 기기(라즈베리파이)에 집어넣습니다.

sub-device 파일을 넣는 위치는 `/opt/damda/sub-devices/user-devices` 입니다.

capability는 `capabilites/` 아래에, 기기 코드는 `functions/` 아래에, profile은 `profiles/` 아래에 추가합니다.

```shell
root@raspberrypi:/opt/damda/sub-devices/user-devices# ls -al
합계 20
drwxr-xr-x 5 root root 4096 10월 14 13:04 .
drwxr-xr-x 4 root root 4096 10월 14 13:04 ..
drwxr-xr-x 2 root root 4096 10월 14 13:04 capabilities
drwxr-xr-x 2 root root 4096 10월 14 13:04 functinos
drwxr-xr-x 2 root root 4096 10월 14 13:04 profiles
```

추가가 완료되면 **DAMDA 기기를 재부팅** 합니다.

재부팅 후 정의한 기기 타입이 추가된 것을 확인할 수 있습니다.
