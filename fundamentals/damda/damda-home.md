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

"메뉴 > 기타 > DAMDA Home"을 통해 실행할 수 있습니다

![](<../../.gitbook/assets/image (16).png>)

Home의 첫화면에서 **시간 및 지역기반 날씨정보**를 확인할 수 있습니다. 또한  Sample과 사용자 컴포넌트 리스트를 확인할 수 있습니다. Install 되자마자는 설치된필수 컴포넌트만 설치되어있으므로 와 같은 안내문구가 나옵니다.

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption><p>DAMDA Home 첫 화면</p></figcaption></figure>

#### 날씨 정보 위치 변경하기&#x20;

'서울특별시 서초구 양재동' 글씨를 클릭하면 원하는 위치로 바꿔서 기상 정보를 확인할 수 있습니다

<figure><img src="../../.gitbook/assets/image (2) (3).png" alt=""><figcaption><p>위치 선택 화면</p></figcaption></figure>

## 설치된 앱목록 확인

DAMDA Console을 통해 배포한 컴포넌트들을 확인할 수 있습니다.\
index.html을 포함한 앱의 경우, 아이콘을 클릭하면 index.html로 이동합니다.

&#x20;index.html을 포함하는 앱을 만드는 방법은 [undefined.md](../damda-cloud/undefined-1/undefined.md "mention")를 확인해주세요.&#x20;

<figure><img src="../../.gitbook/assets/image (43).png" alt=""><figcaption><p>Home 앱에서 설치된 컴포넌트(앱) 목록 확인</p></figcaption></figure>

## ThinQ 연동하기

DAMDA가 설치된 기기를 ThinQ에 내 제품으로 등록할 수 있습니다.&#x20;

기기 등록하는 방법은 [undefined.md](../page-1/damda-home/undefined.md "mention")를 확인해주시기 바랍니다

\
기기 등록이 완료되면 ThinQ앱에서 'DAMDA 제품' 카드가 생성된 것을 확인할 수 있습니다.&#x20;

<img src="../../.gitbook/assets/image (4) (6).png" alt="" data-size="original">

{% hint style="info" %}
com.damda.sample.damda-hub 을 설치한 경우, 기기 카드를 누르면 hub앱을 위해 만들어진 IHM을 확인할 수 있습니다.

<mark style="color:orange;">현재 com.damda.sample.damda-hub을 설치 후 ThinQ앱을 통한TV제어에 버그가 발견되어 제어가 정상적으로 동작하지 않고 있습니다. 버그 수정 작업 진행 중입니다.</mark>
{% endhint %}
