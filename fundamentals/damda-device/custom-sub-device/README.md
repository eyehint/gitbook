# Custom Sub Device

{% hint style="info" %}
DAMDA Console을 통해 com.damda.sample.damda-hub를 설치한 후 사용할 수 있는 기능입니다.
{% endhint %}

DAMDA 에서는 새로운 기기 타입을 추가하여 연동 및 제어를 해볼 수 있습니다.

새로운 기기를 자유롭게 만든 후, 기기와 hub간에 통신할 수 있도록 아래 3가지를 만들어야 합니다.

1. [Capability 생성](capability.md)
2. [Profile 생성](profile.md)
3. [기기 코드 추가](functions.md)

com.damda.sample.damda-hub 설치 시, sub-devices가 함께 설치됩니다. `/opt/damda/sub-devices/damda-devices/` 밑에서 기본적으로 정의된 sub-devices들을 확인할 수 있습니다. 이 샘플 기기 들은 [DAMDA Hub 앱](../../../reference/samples/damda-hub.md)에서 등록, 제어 등을 하면서 사용해볼 수 있습니다.&#x20;

이 가이드에 따라 capability, profile, functions를 정의하면 hub와 통신하여 새로 정의한 서브디바이스 타입을 제어할 수 있습니다.

작성한 파일들은 경로에 맞춰 DAMDA 기기(라즈베리파이)에 집어넣습니다.

sub-device 파일을 넣는 위치는 `/opt/damda/sub-devices/user-devices` 입니다.

capability는 `capabilites/` 아래에, 기기 코드는 `user-functions/` 아래에, profile은 `profiles/` 아래에 추가합니다.

```shell
root@raspberrypi:/opt/damda/sub-devices/user-devices# ls -al
합계 20
drwxr-xr-x 5 root root 4096 10월 14 13:37 .
drwxr-xr-x 4 root root 4096 10월 14 13:04 ..
drwxr-xr-x 2 root root 4096 10월 14 13:04 capabilities
drwxr-xr-x 2 root root 4096 10월 14 13:04 user-functions
drwxr-xr-x 2 root root 4096 10월 14 13:04 profiles
```

추가가 완료되면 <mark style="color:red;">**DAMDA 기기를 재부팅**</mark> 합니다.

재부팅 후 정의한 기기 타입이 추가된 것을 [DAMDA Hub 앱](../../../reference/samples/damda-hub.md)에서 확인할 수 있습니다.
