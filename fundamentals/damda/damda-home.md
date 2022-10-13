---
description: >-
  DAMDA의 메인 화면입니다. DAMDA 기기를 ThinQ와 연동하기 위한 QR Login, 설치한 컴포넌트 목록, 그리고 DAMDA
  Hub를 제공합니다.
---

# DAMDA Home

{% hint style="info" %}
DAMDA 설치 후 사용할 수 있습니다
{% endhint %}

## Home 실행하기

"메뉴 > 기타 > DAMDA Home"을 통해 실행할 수 있습니다

![](<../../.gitbook/assets/image (18).png>)

// Home 캡처 변경 필요&#x20;

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>DAMDA Home 시작 화면 </p></figcaption></figure>

## 설치된 앱목록 확인

DAMDA Console을 통해 배포한 앱들을 확인할 수 있습니다.\
index.html을 포함한 앱의 경우, 아이콘을 클릭하면 index.html로 이동합니다. 자세한 [컴포넌트 생성 방법](../damda-cloud/undefined.md#undefined)은 가이드를 확인해주세요. \
DAMDA Hub를 클릭하면 DAMDA에서 제공하는 허브 기능을 사용해볼 수 있습니다.

// 캡처

## ThinQ 연동하기

DAMDA가 설치된 기기를 ThinQ에 내 제품으로 등록할 수 있습니다.

PinCode 혹은 QR 을 통해 ThinQ에 로그인할 수 있는 화면이 나타납니다. \
가이드에 따라 스마트폰의 ThinQ앱을 실행시켜 앱의 로그인 정보를 허브에 공유합니다. \
공유된 계정에 DAMDA가 설치된 기기를 등록하게 됩니다. \
ThinQ앱에서 'DAMDA 제품'이라는 이름으로 확인할 수 있습니다.&#x20;



ThinQ앱에서 'DAMDA 제품' 카드를 클릭하면 DAMDA Hub와 연결된 서브기기를 제어할 수 있습니다. DAMDA Hub에 기기를 등록하는 방법은 ['서브기기 연동하기'](damda-home.md#undefined-1)를 참고해주세요. \


TPA를 통해 나만의 카드를 만들어서 DAMDA에 설치한 내 컴포넌트와 통신할 수도 있습니다.&#x20;

## DAMDA Hub 사용하기

DAMDA가 허브가 되어 동작합니다.&#x20;

### 서브기기 연동하기

허브와 같은 네트워크상에 있는 서브기기들을 연동시켜 볼 수 있습니다. 기본적으로 연동 가능한 기기 타입은 motionCamera, sensorLight, webOSTV, sensorThermoHygrometer 입니다.\
webOSTV를 제외한 나머지 타입들은 시뮬레이터와 연동 하게 됩니다. 시뮬레이터는 해커톤 전에 제공될 예정입니다.&#x20;

"추가하기"버튼을 눌러 서브 디바이스의 타입과 연결 하기위한 정보들을 입력합니다.

#### TV 등록하기 예시&#x20;

webOSTV가 같은 네트워크 상에 있다면, TV를 등록하고 제어 해볼 수 있습니다.&#x20;

1. TV를 구분할 alias 를 입력해줍니다
2. TV의 IP정보를 입력해줍니다
3. "추가하기"버튼을 눌러줍니다.\
   ![](<../../.gitbook/assets/image (21).png>)\

4. 잠시 기다리면 TV 카드가 추가된 것을 확인할 수 있습니다.\
   ![](<../../.gitbook/assets/image (12).png>)

### 서브기기 제어하기

연동된 서브기기들을 제어 해볼 수 있습니다. 서브기기 카드를 누르면 제어 할 수 있는 화면이 나옵니다. 제어 목록은 기기의 capability를 바탕으로 생성됩니다.

나만의 기기 타입을 만들면 허브를 통해 내가 만든 기기를 등록하고 제어  수 있습니다. \
커스텀 기기 타입을 만드는 방법은 (여기-링크추가)를 참고하시기 바랍니다

#### TV 제어하기

1. TV 카드를 누릅니다.&#x20;
2. 기기 제어 패널에서 setVolume에 원하는 값을 입력합니다. \
   ![](<../../.gitbook/assets/image (2) (1).png>)
3. "실행하기"를 클릭합니다.&#x20;
4. TV의 볼륨이 2로 설정됩니다.&#x20;
