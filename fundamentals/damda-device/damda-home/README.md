---
description: >-
  DAMDA의 메인 화면입니다. DAMDA 기기를 ThinQ와 연동하기 위한 QR Login, 설치한 컴포넌트 목록, 그리고 DAMDA
  Hub를 제공합니다.
---

# DAMDA Home

{% hint style="info" %}
DAMDA 설치 후 사용할 수 있습니다
{% endhint %}

## DAMDA Home 시작하기

"메뉴 > 기타 > DAMDA Home"을 통해 실행할 수 있습니다. 혹은 라즈베리파이에서 브라우저를 직접실행하여 localhost:5001로도 접속할 수 있습니다.

![](<../../../.gitbook/assets/image (16).png>)



Home의 첫화면에서 **시간 및 지역기반 날씨정보**를 확인할 수 있습니다. 또한  Sample과 사용자 컴포넌트 리스트를 확인할 수 있습니다. Install 직후에는 필수 컴포넌트만 설치되어있으므로 와 같은 안내 문구가 나옵니다.

<figure><img src="../../../.gitbook/assets/image (18) (1).png" alt=""><figcaption><p>DAMDA Home 첫 화면</p></figcaption></figure>

#### 날씨 정보 위치 변경하기&#x20;

'서울특별시 서초구 양재동' 글씨를 클릭하면 원하는 위치로 바꿔서 기상 정보를 확인할 수 있습니다

<figure><img src="../../../.gitbook/assets/image (2) (3) (2).png" alt=""><figcaption><p>위치 선택 화면</p></figcaption></figure>

## 앱 테마 변경

우측 상단의 "DAMDA"를 클릭하면 앱 테마가 변경됩니다. 맘에 드는 색상으로 사용해 보세요 :sparkles:

## 설치된 앱목록 확인

DAMDA Console을 통해 배포한 컴포넌트들을 확인할 수 있습니다. 이 때 컴포넌트 중 샘플 컴포넌트와 커스텀 컴포넌트만 목록에 보이게 됩니다. 컴포넌트 명이 com.damda.necessary로 시작하는 컴포넌트와 com.damda.public으로 시작하는 컴포넌트는 보이지 않습니다.

index.html을 포함한 앱의 경우, 아이콘을 클릭하면 index.html로 이동합니다.

&#x20;index.html을 포함하는 앱을 만드는 방법은 [develop-component-code.md](../../damda-cloud/manage-component/develop-component-code.md "mention")를 확인해주세요.&#x20;

<figure><img src="../../../.gitbook/assets/image (43).png" alt=""><figcaption><p>Home 앱에서 설치된 컴포넌트(앱) 목록 확인</p></figcaption></figure>

## ThinQ 연동하기

DAMDA가 설치된 기기를 ThinQ에 내 제품으로 등록할 수 있습니다.&#x20;

기기 등록하는 방법은 [register-device.md](register-device.md "mention")를 확인해주시기 바랍니다

\
기기 등록이 완료되면 ThinQ앱에서 'DAMDA 제품' 카드가 생성된 것을 확인할 수 있습니다.&#x20;

<img src="../../../.gitbook/assets/image (4) (6).png" alt="" data-size="original">



ThinQ에 제품으로 등록하고 나면, TPA를 통해 나만의 카드를 만들어서 DAMDA에 설치한 내 컴포넌트와 통신할 수 있습니다. 컴포넌트는 [thinq-api.md](../../../reference/api-reference/thinq-api.md "mention")를 사용하여 TPA와 데이터를 주고받을 수 있습니다.

이러한 방법으로 만들어진 [connect-with-thinq.md](../../../quick-start/connect-with-thinq.md "mention") 샘플을 참고하실 수 있습니다.

{% hint style="info" %}
TPA 개발 가이드: [https://thinqapp.developer.lge.com/ko/documentation/development/ihm-development/ihm\_development\_guide/](https://thinqapp.developer.lge.com/ko/documentation/development/ihm-development/ihm\_development\_guide/)
{% endhint %}

{% hint style="info" %}
com.damda.sample.damda-hub 을 설치한 경우, 기기 카드를 누르면 hub앱을 위해 만들어진 IHM을 확인할 수 있습니다.

<mark style="color:orange;">현재 com.damda.sample.damda-hub을 설치 후 ThinQ앱을 통한TV제어에 버그가 발견되어 제어가 정상적으로 동작하지 않고 있습니다. 버그 수정 작업 진행 중입니다.</mark>
{% endhint %}
