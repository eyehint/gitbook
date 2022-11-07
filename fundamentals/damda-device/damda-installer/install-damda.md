---
description: DAMDA Installer를 사용하여 DAMDA를 설치합니다
---

# DAMDA 설치하기

## Prerequisites

DAMDA Installer를 설치해두어야 합니다. [setup-damda-installer.md](setup-damda-installer.md "mention")를 확인하세요

## Install DAMDA

GUI 혹은 CLI를 사용하여 설치 할 수 있습니다.

### GUI

DAMDA Installer 아이콘을 눌러서 실행합니다.&#x20;

<figure><img src="../../../.gitbook/assets/menu_installer.png" alt=""><figcaption><p>RaspberryPi OS / Ubuntu mate</p></figcaption></figure>

DAMDA 계정과 디바이스를 연동하기위하여 DAMDA계정으로 로그인을 진행합니다.\
Installer에 DAMDA id와 password 입력합니다.&#x20;

<figure><img src="../../../.gitbook/assets/image (17) (1).png" alt=""><figcaption><p>Installer 로그인 창</p></figcaption></figure>

"Install" 버튼 클릭합니다.&#x20;

<figure><img src="../../../.gitbook/assets/image (7) (4).png" alt=""><figcaption><p>Install / Uninstall 선택화면</p></figcaption></figure>

설치가 완료되면 "Next" 버튼을 눌러 다음단계로 이동합니다. \
(설치 과정은 약 10분 정도 소요됩니다. 네트워크 환경에 따라 더 오래 소요될 수 있습니다.)

<figure><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FiVEw9LLe2TVUGYZgOPBq%2Fimage.png?alt=media&#x26;token=7bd85b06-c8f6-468d-a9fb-79c896a2a43b" alt=""><figcaption><p>설치 진행 중</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (3) (3) (1).png" alt=""><figcaption><p>설치 완료 상태</p></figcaption></figure>

설치 과정이 완료 된 것을 확인합니다. \
앞으로 컴포넌트 배포할 때 필요한 정보인, DAMDA 기기명을 확인할 수 있습니다.

<figure><img src="../../../.gitbook/assets/image (37) (1).png" alt=""><figcaption><p>설치 완료 확인</p></figcaption></figure>

### CLI

damda install 명령을 sudo 로 실행합니다

```shell
sudo damda install
```

DAMDA 계정과 디바이스를 연동하기위하여 DAMDA계정으로 로그인을 진행합니다.\
DAMDA id와 password 입력합니다.

```shell
DAMDA ID: XXXX@lge.com
DAMDA PW:
Installing  [####################################]  100%
Device ID: Damda-V2-XXXXXXXXXX
```

설치가 완료되면 Device ID를 확인할 수 있습니다.\


## Confirm Installation

설치 완료 화면에서 ID 확인을 못한 경우 **Installer를 다시 실행**해서 확인할 수도 있습니다.

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption><p>Installer 첫화면에서 기기명 확인</p></figcaption></figure>

****\
**terminal에서 damda info 명령**을 통해서도 생성된 디바이스 ID를 확인할 수 있습니다.

```shell
$ sudo damda info
DAMDA Device ID: Damda-V2-ZAhi2pjmSpatGd4ITFl5zA
```

****\
****[**DAMDA Console**](http://damda.lge.com/)**의 디바이스 탭**에서 동일한 디바이스 ID로 기기가 생성된 것을 확인할 수 있습니다.

<figure><img src="../../../.gitbook/assets/image (5) (3).png" alt=""><figcaption><p>DAMDA Console 디바이스 탭에서 기기명 확인</p></figcaption></figure>
