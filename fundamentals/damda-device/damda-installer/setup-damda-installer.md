---
description: DAMDA를 설치하기 위한 DAMDA Installer 입니다
---

# DAMDA Installer 설치하기

DAMDA 를 설치하기 위해서, installer 패키지를 다운받고, 설치합니다.&#x20;

Installer를 설치하고 나면, 메뉴에서 damda installer가 생성된 것을 확인할 수 있습니다.&#x20;

RaspbrerryPi OS와 Ubuntu mate를 지원합니다.

## 필수 패키지 설치

필수 패키지 들을 설치합니다. damda 개발환경은 python3을 사용합니다. docker 및 nodejs mosquitto가 기본적으로 함께 설치됩니다.

```shell
sudo apt install -y default-jdk unzip curl python3-pip libatlas-base-dev proj-bin proj-data libproj-dev libgeos-dev libgdal-dev python3-virtualenv docker.io docker-compose npm nodejs mosquitto mosquitto-clients
```

## Download Installer Setup File

Installer setup 파일을 다운 받습니다. 이 setup 파일을 설치하고 나면, damda installer 가 생성됩니다.

{% hint style="warning" %}
설치 파일 사내용으로 공개합니다. 사내망에서 다운받아 주시기 바랍니다.&#x20;

업데이트 중인 기능들이 있어 일부 정상동작하지 않을 수 있습니다.
{% endhint %}

Installer setup 파일:&#x20;

* Raspberry Pi OS: damda-installer\_1.0.3-1\_pi.deb
* Ubutu: damda-installer\_1.0.3-1\_ubuntu.deb

{% code title="Raspberry Pi" %}
```shell
# curl -O http://10.178.133.16/damda-installer_1.0.3-1_pi.deb
```
{% endcode %}

{% code title="Ubuntu" %}
```shell
# 업데이트 예
```
{% endcode %}

## Setup Installer

* DAMDA 사용자들만 installer 패키지를 받을 수 있습니다. 명령어 입력 후, 잠시 기다리면 DAMDA 계정을 입력하도록 메세지가 나옵니다.&#x20;
* DAMDA 계정을 입력할 때 까지 설치가 진행되지 않습니다.&#x20;
* DAMDA 계정 입력이 잘못 된 경우 설치가 종료 되므로, 다시 설치 명령어를 입력해주시기 바랍니다.

{% code title="Raspberry Pi" %}
```shell
sudo apt install ./damda-installer_1.0.3-1_pi.deb
```
{% endcode %}

{% code title="설치 진행 중..." %}
```shell
...
DAMDA ID: XXXX@lge.com
DAMDA PW:
...
Progress: [ 20%] [####################################................................................................................................................................................]
```
{% endcode %}



&#x20;Ubuntu에서는 설치 파일명에 맞춰 아래 명령어를 사용합니다

{% code title="Ubuntu" %}
```shell
sudo apt install ./damda-installer_1.0.3-1_ubuntu.deb
```
{% endcode %}



{% hint style="info" %}
설치 후, 아래와 같이 커널 업그레이드 안내가 나오는 경우가 있습니다.\
확인하고 계속 진행해주세요\
<img src="../../../.gitbook/assets/image (6) (3) (1).png" alt="" data-size="original">
{% endhint %}

## Installer Setup 완료 확인

damda version 확인을 통해 installer 설치가 완료 되었는지 확인할 수 있습니다.

```shell
sudo damda --version
```

설치가 완료되면 아래와 같이 버전명을 확인할 수 있습니다.

```
DAMDA Installer CLI Version: 1.0.3
```

각 시스템의 메뉴에서도 Installer 아이콘이 생성된 것을 확인할 수 있습니다.

<figure><img src="../../../.gitbook/assets/menu_installer.png" alt=""><figcaption><p>RaspberryPi OS / Ubuntu mate</p></figcaption></figure>
