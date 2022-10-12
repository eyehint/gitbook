---
description: DAMDA를 사용하기 위한 환경 설정 방법입니다
---

# Step1. 개발환경 구성

## Setup Environment <a href="#setup-environment" id="setup-environment"></a>

### Step1: Prerequisites

* DAMDA 계정
  * DAMDA 환경을 구성하기 위해 DAMDA 계정이 필요합니다
  * DAMDA 계정이 없는 경우, [DAMDA Console](http://damda.lge.com/login?redirect=%2Fhome) 로 이동하여 계정 생성합니다\
    계정 생성 가이드 (링크)
* RaspberryPi 4 준비
  * RaspberryPi에 OS를 설치해서 사용할 준비를 합니다
  * 지원 OS는 **RaspberryPi OS(권장)**, Ubuntu mate 입니다
    * Raspberry Pi OS 공식 페이: [https://www.raspberrypi.com/software/](https://www.raspberrypi.com/software/)
    * &#x20;Ubuntu MATE for Raspberry Pi 공식 페이: [https://ubuntu-mate.org/raspberry-pi/](https://ubuntu-mate.org/raspberry-pi/)

### Step2: Install the library

필수 패키지 들을 설치합니다

```shell
sudo apt install -y default-jdk unzip curl python3-pip libatlas-base-dev proj-bin proj-data libproj-dev libgeos-dev libgdal-dev python3-virtualenv docker.io docker-compose npm nodejs
```

### Step3: Download Installer

Installer setup 파일을 다운 받습니다

Installer setup 파일:&#x20;

* Raspberry Pi OS: damda-installer\_1.0.3-1\_pi.deb
* Ubutu: damda-installer\_1.0.3-1\_ubuntu.deb

{% code title="Raspberry Pi" %}
```shell
curl -O https://damda-component-artifacts.s3.ap-northeast-2.amazonaws.com/installer/1.0.3/damda-installer_1.0.3-1_pi.deb
```
{% endcode %}

{% code title="Ubuntu" %}
```shell
curl -O https://damda.s3.ap-northeast-2.amazonaws.com/installer/damda-installer_1.0.3-1_ubuntu.deb
```
{% endcode %}

## Setup Installer

{% tabs %}
{% tab title="Installer 설치" %}
* DAMDA 사용자들만 installer 패키지를 받을 수 있습니다. 명령어 입력 후, 잠시 기다리면 DAMDA 계정을 입력하도록 메세지가 나옵니다.&#x20;
* DAMDA 계정을 입력할 때 까지 설치가 진행되지 않습니다.&#x20;
* DAMDA 계정 입력이 잘못 된 경우, [Installer를 제거](../fundamentals/damda/damda-installer/remove-damda-installer.md)하고 다시 설치 진행해야합니다.

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
{% endtab %}

{% tab title="Installer 설치 확인" %}
damda version 확인을 통해 installer 설치가 완료 되었는지 확인할 수 있습니다.

```shell
sudo damda --version
```

설치가 완료되면 아래와 같이 버전명을 확인할 수 있습니다

```
DAMDA Installer CLI Version: 1.0.3
```
{% endtab %}
{% endtabs %}

## Install DAMDA

{% tabs %}
{% tab title="GUI" %}
1. DAMDA Installer 아이콘을 눌러서 실행합니다\
   \[RaspberryPi OS]                                         \[Ubuntu mate]\
   ![](<../.gitbook/assets/image (7) (2).png>)   ![Menu > "damda" 검색](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2Fo39jplzTATPRX20mYEYA%2Fimage.png?alt=media\&token=df171290-7f44-4663-8051-69634d1bca2d)\

2. Installer에 DAMDA id와 password 입력합니다\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FfrLwzBJnl9AwXT8JUcwk%2Fimage.png?alt=media\&token=1c2059d0-6a04-479a-b65f-bb9427f9e038)\

3. "Install" 버튼 클릭합니다\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2F864kgxVwYclEkleIzerW%2Fimage.png?alt=media\&token=033a5c0f-44ac-4158-8ed8-16e7b5c366df)\

4. 설치가 완료되면 "Next" 버튼을 눌러 다음단계로 이동합니다 \
   (설치 과정은 약 10분 정도 소요됩니다. 네트워크 환경에 따라 더 오래 소요될 수 있습니다.)\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FiVEw9LLe2TVUGYZgOPBq%2Fimage.png?alt=media\&token=7bd85b06-c8f6-468d-a9fb-79c896a2a43b) ​![](<../.gitbook/assets/image (2) (3).png>)\

5. 설치 과정이 완료 된 것을 확인합니다\

6.  DAMDA 디바이스가 설치되었습니다. [DAMDA Console](http://damda.lge.com/)의 디바이스 탭에 기기가 생성된 것을 확인할 수 있습니다\


    <figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="CLI" %}
damda install 명령을 sudo 로 실행합니다

```shell
sudo damda install
```



설치가 진행되면, DAMDA 계정을 다시 한번 입력해야 합니다

```shell
DAMDA ID: XXXX@lge.com
DAMDA PW:
Installing  [####################################]  100%
Device ID: Damda-V2-XXXXXXXXXX
```



설치가 완료되면 [damda console](http://damda.lge.com/home)에 디바이스가 만들어 진 것을 확인할 수 있습니다\
/// e디바이스 생성 화면 추
{% endtab %}
{% endtabs %}
