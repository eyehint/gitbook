---
description: Installer 를 삭제하는 가이드 입니다
---

# DAMDA Installer 삭제하기

{% hint style="warning" %}
Installer를 삭제하면 DAMDA 를 사용할 수 없습니다! 안정적인 동작을 위해 DAMDA를 제거한 후, Installer를 삭제하는 것을 권장합니다
{% endhint %}



apt를 이용하여 damda-installer 패키지를 제거합니다

```shell
sudo apt remove damda-installer
```

damda version 확인 명령을 사용하여 제거가 완료 되었는지 확인할 수 있습니다

```shell
sudo damda --version
```

정상적으로 제거된 경우 아래와 같이 damda 명령을 찾을 수 없습니다

```shell
sudo: damda: command not found
```
