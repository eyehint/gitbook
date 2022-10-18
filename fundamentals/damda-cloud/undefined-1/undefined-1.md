---
description: DAMDA를 통해 컴포넌트 배포하는 방법 가이드 입니다
---

# 컴포넌트 배포하기

## 컴포넌트 선택

DAMDA Console에 접속하여 컴포넌트 탭으로 이동합니다.

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>컴포넌트 탭 화면</p></figcaption></figure>

'내 컴포넌트' 중 배포하고 싶은 컴포넌트를 선택하고 배포하기를 클릭합니다.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption><p>배포할  컴포넌트 선택</p></figcaption></figure>

{% hint style="info" %}
내 컴포넌트가 하나라도 포함되야 배포하기 클릭이 가능합니다. (UI 개선 예정입니다)&#x20;

내 컴포넌트 생성 방법은 [컴포넌트 생성하기](undefined.md)을 참조하세요
{% endhint %}

## 배포하기 목록 확인

배포 작업 생성 팝업이 나타납니다. 이 팝업에 포함된 배포할 목록을 검토합니다.

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

배포 목록에는 퍼블릭 컴포넌트 전체가 자동으로 추가됩니다. 원하지 않는 퍼블릭 컴포넌트는 제외하고 배포합니다.

{% hint style="warning" %}
제외된 컴포넌트는 damda 기기에서 삭제됩니다. 계속 사용하고 싶은 컴포넌트는 항상 추가해주시기 바랍니다.
{% endhint %}

'배포 대상'에 원하는 damda 기기명을 선택해줍니다.&#x20;

'배포 요청' 버튼을 누르면 배포를 진행할 것인지 확인하는 팝업이 나타납니다.

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

'예'를 누르면 배포가 시작됩니다. 배포가 완료되는 것을 기다립니다. 이 창을 닫아도 배포는 계속 진행됩니다.

{% hint style="warning" %}
현재 [배포 준비에서 UI가 진행되지 않는 버그](undefined-1.md#known-issue)가 있습니다. 배포가 정상적으로 진행중이니, 배포 완료 여부를 기기 정보 페이지에서 확인해주시기 바랍니다.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Known Issue

1. "배포 준비" 단계에서 UI가 변경되지 않는 버그가 있습니다. DAMDA Console이나 라즈베리파이 상의 디버깅 콘솔을 통해 배포 완료 여부를 확인할 수 있습니다.

## TroubleShooting

<details>

<summary>배포 완료 후 컴포넌트 상태가 'Broken' 일 때 </summary>

컴포넌트에 정의된 스크립트들을 실행하던 도중 에러가 발생하면 Broken 상태가 됩니다. 다양한 원인이 있으나 아래와 같은 케이스에 해당하는지 확인 할 수 있습니다.

1. 스크립트경로에 zip파일명이 빠진 경우:  "{root}/zip파일명/코드파일경로" 로 작성되어야 합니다. \
   [컴포넌트 배포 따라하기](../../../quick-start/step2..md#3.-zip-damda)에서 간단한 예제를 확인할 수 있습니다.

</details>

<details>

<summary>이전에 설치한 컴포넌트가 보이지 않습니다.</summary>

사라진 컴포넌트가 배포에 포함되었는지 다시 한번 확인 합니다. 배포 시 선택하지 않은 컴포넌트들은, 디바이스에서 삭제 됩니다. 디바이스에서 계속 사용할 컴포넌트는 항상 배포에 포함시켜주어야 합니다.

</details>
