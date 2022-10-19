---
description: DAMDA를 통해 컴포넌트 배포하는 방법 가이드 입니다
---

# 컴포넌트 배포하기

## 컴포넌트 선택

DAMDA Console에 접속하여 컴포넌트 탭으로 이동합니다.

<figure><img src="../../../.gitbook/assets/image (7) (2).png" alt=""><figcaption><p>컴포넌트 탭 화면</p></figcaption></figure>

'내 컴포넌트' 중 배포하고 싶은 컴포넌트를 선택하고 배포하기를 클릭합니다.

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption><p>배포할  컴포넌트 선택</p></figcaption></figure>

{% hint style="info" %}
내 컴포넌트가 하나라도 포함되야 배포하기 클릭이 가능합니다.&#x20;

따라서 '퍼블릭 컴포넌트만' 배포하고 싶다면 우선 내 컴포넌트를 하나 선택하고 '배포하기'를 누른뒤, 배포 목록에서 선택했던 내 컴포넌트를 제외해 주세요 (조금 더 편리한 배포가 가능하도록 UI 개선 예정입니다 :star:)

내 컴포넌트 생성 방법은 [컴포넌트 생성하기](undefined.md)을 참조하세요
{% endhint %}

## 배포하기 목록 확인

배포 작업 생성 팝업이 나타납니다. 이 팝업에 포함된 배포할 목록을 검토합니다.

<figure><img src="../../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

배포 목록에는 퍼블릭 컴포넌트 전체가 자동으로 추가됩니다. 원하지 않는 퍼블릭 컴포넌트는 제외하고 배포합니다.

{% hint style="danger" %}
**제외된 컴포넌트는 damda 기기에서 삭제됩니다. 계속 사용하고 싶은 컴포넌트는 항상 추가해주시기 바랍니다.**
{% endhint %}

'배포 대상'에 원하는 damda 기기명을 선택해줍니다.&#x20;

'배포 요청' 버튼을 누르면 배포를 진행할 것인지 확인하는 팝업이 나타납니다.

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption><p>배포 생성 확인 팝업</p></figcaption></figure>

'예'를 누르면 배포가 시작됩니다. 배포가 완료되는 것을 기다립니다. 이 창을 닫아도 배포는 계속 진행됩니다.

{% hint style="warning" %}
현재 [배포 준비에서 UI가 진행되지 않는 버그](undefined-1.md#known-issue)가 있습니다. 배포가 정상적으로 진행중이니, 배포 완료 여부를 [기기 정보 페이지에서 확인](undefined-1.md#damda)해주시기 바랍니다.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (7) (6).png" alt=""><figcaption><p>배포 진행 중</p></figcaption></figure>

## 배포 결과 확인하기

### DAMDA 콘솔에서 확인하기&#x20;

Damda Console에서 디바이스 탭으로 이동합니다. \


<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

배포한 기기의 명 오른쪽에 <mark style="color:blue;">Details</mark>를 클릭합니다. 기기 세부 정보 창이 나타납니다. 이 창에서 배포 상태와 컴포넌트 상태를 확인합니다.

{% hint style="info" %}
DAMDA에서 필요한 필수 컴포넌트들은 항상 함께 배포 됩니다. 따라서 컴포넌트 상태 창에는 직접 배포하지 않은 컴포넌트가 존재할 수 있습니다.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

마지막 배포 기준으로 배포상태가 업데이트 되므로, 배포한 시간이 맞는지 확인합니다. \
배포상태가 **COMPLETE, SUCCESSFUL**이면 배포가 성공한 것입니다. \
COMPLETE, SUCCESSFUL이 아닌 경우는 [배포가 정상으로 완료되지 않을 때](undefined-1.md#undefined-4) 를 확인해보시기 바랍니다.

컴포넌트 상태가 Broken 인 것은 컴포넌트가 정상적으로 설치되지 않은 것을 의미합니다. [배포 완료 후 컴포넌트 상태가 'Broken' 일 때](undefined-1.md#broken)  참고해보시기 바랍니다.

### DAMDA 기기에서 확인하기

업데이트 예정입니다.

### 디버깅 콘솔에서 확인하기

업데이트 예정입니다.

### index.html 확인하기

업데이트 예정입니다.



## Known Issue

1. "배포 준비" 단계에서 UI가 변경되지 않는 버그가 있습니다. DAMDA Console이나 라즈베리파이 상의 디버깅 콘솔을 통해 배포 완료 여부를 확인할 수 있습니다.

## TroubleShooting

<details>

<summary>배포가 정상으로 완료되지 않을 때</summary>

다양한 원인으로 배포가 실패할 수 있습니다.&#x20;

우선 damda 기기(라즈베리파이)가 **인터넷에 접속되어 있는지** 확인합니다.&#x20;

만약 **기기를 부팅한지 얼마 안됐다면**, 아직 damda가 실행 준비중일 수 있습니다. 5분정도 기다렸다가 다시 시도해주세요.&#x20;

위와 같은 상황이 아닌데도 배포가 실패했다면 **지원이 필요한 상황**입니다. damda 기기에서 디버깅 콘솔을 통해 이슈 전송을 해주세요

</details>

<details>

<summary>배포 완료 후 컴포넌트 상태가 'Broken' 일 때 </summary>

컴포넌트에 정의된 스크립트들을 실행하던 도중 에러가 발생하면 Broken 상태가 됩니다. 다양한 원인이 있으나 아래와 같은 케이스에 해당하는지 확인 할 수 있습니다.

* 스크립트경로에 zip파일명이 빠진 경우:  \
  "{root}/zip파일명/코드파일경로" 로 작성되어야 합니다. [컴포넌트 배포 따라하기](../../../quick-start/step2..md#3.-zip-damda)에서 간단한 예제를 확인할 수 있습니다.
* 코드에 올린 'zip 파일명'과 스크립트 경로상 'zip 파일명'이 동일하지 않은 경우:\
  경로 문제가 생겨 코드가 정상적으로 실행되지 않을 수 있습니다. 업로드한 파일명과 스크립트를 다시 한번 확인 부탁드립니다.
* zip 파일 압축 해제 했을 때, 실행파일 경로가 바로 존재하지 않는 경우:
  * 예시\
    <mark style="color:green;">(정상)</mark> hellodamda.zip 해제 -> hellodamda/app.py  \
    <mark style="color:red;">(에러)</mark> hellodamda.zip 해제 -> hellodamda/hellodamda/app.py

</details>

<details>

<summary>이전에 설치한 컴포넌트가 보이지 않습니다.</summary>

사라진 컴포넌트가 배포에 포함되었는지 다시 한번 확인 합니다. 배포 시 선택하지 않은 컴포넌트들은, 디바이스에서 삭제 됩니다. 디바이스에서 계속 사용할 컴포넌트는 항상 배포에 포함시켜주어야 합니다.

</details>
