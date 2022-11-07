---
description: DAMDA를 통해 컴포넌트 배포하는 방법 가이드 입니다
---

# 컴포넌트 배포하기

## 컴포넌트 선택

DAMDA Console에 접속하여 컴포넌트 탭으로 이동합니다.

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption><p>컴포넌트 탭 화면</p></figcaption></figure>

'내 컴포넌트' 중 배포하고 싶은 컴포넌트를 선택하고 배포하기를 클릭합니다.

<figure><img src="../../../.gitbook/assets/image (29).png" alt=""><figcaption><p>배포할 컴포넌트 선택</p></figcaption></figure>

선택한 컴포넌트 없이 배포하는 경우에는 기기가 <mark style="color:red;">초기화</mark> 됩니다

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption><p>기기 초기화 진행 여부 팝업</p></figcaption></figure>

## 배포하기 목록 확인

배포 작업 생성 팝업이 나타납니다. 이 팝업에 포함된 배포할 목록을 검토합니다.

<figure><img src="../../../.gitbook/assets/image (42) (2).png" alt=""><figcaption><p>배포 작업 설정 화면 (컴포넌트 목록 편집, 배포할 기기 선택)</p></figcaption></figure>

퍼블릭 컴포넌트가 추천 목록에 포함되어 있습니다. 사용하고 싶은 컴포넌트는 <mark style="color:green;">**"추가"**</mark> 버튼을 눌러 선택해줍니다.

제공되는 샘플 앱들은 각각 동작을 위해 필요한 퍼블릭 컴포넌트가 있으니, 가이드 확인 후 사용해주시기 바랍니다.

{% hint style="danger" %}
**제외된 컴포넌트는 damda 기기에서 삭제됩니다. 계속 사용하고 싶은 컴포넌트는 항상 **<mark style="color:green;">**추가**</mark>**해주시기 바랍니다.**
{% endhint %}

'배포 대상'에 원하는 damda 기기명을 선택해줍니다.&#x20;

'배포 요청' 버튼을 누르면 배포를 진행할 것인지 확인하는 팝업이 나타납니다.

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption><p>배포 생성 확인 팝업</p></figcaption></figure>

'예'를 누르면 배포가 시작됩니다. 배포가 완료되는 것을 기다립니다. 이 창을 닫아도 배포는 계속 진행됩니다.

{% hint style="warning" %}
현재 간혹 [배포 준비에서 UI가 진행되지 않는 버그](deploy-component.md#known-issue)가 있습니다. UI가 변경되지 않더라도 배포는 정상적으로 진행중입니다. 배포 완료 여부를 [기기 정보 페이지에서 확인](deploy-component.md#damda)해주시기 바랍니다.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (28).png" alt=""><figcaption><p>배포 진행 중</p></figcaption></figure>

{% hint style="info" %}
배포작업 팝업을 종료해도 배포는 계속 진행됩니다
{% endhint %}

## 배포 결과 확인하기

### DAMDA 콘솔에서 확인하기&#x20;

Damda Console에서 디바이스 탭으로 이동합니다.&#x20;

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption><p>디바이스 탭 화면</p></figcaption></figure>

배포한 기기의 명 오른쪽에 <mark style="color:blue;">Details</mark>를 클릭합니다. 기기 세부 정보 창이 나타납니다. 이 창에서 배포 상태와 컴포넌트 상태를 확인합니다.

{% hint style="info" %}
DAMDA에서 필요한 필수 컴포넌트들은 항상 함께 배포 됩니다. 따라서 컴포넌트 상태 창에는 직접 배포하지 않은 컴포넌트가 존재할 수 있습니다.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (1) (11).png" alt=""><figcaption><p>디바이스 상세 정보</p></figcaption></figure>

마지막 배포 기준으로 배포상태가 업데이트 되므로, 배포한 시간이 맞는지 확인합니다. \
배포상태가 **COMPLETE, SUCCESSFUL**이면 배포가 성공한 것입니다. \
COMPLETE, SUCCESSFUL이 아닌 경우는 [배포가 정상으로 완료되지 않을 때](deploy-component.md#undefined-4) 를 확인해보시기 바랍니다.

컴포넌트 상태가 Broken 인 것은 컴포넌트가 정상적으로 설치되지 않은 것을 의미합니다. [배포 완료 후 컴포넌트 상태가 'Broken' 일 때](deploy-component.md#broken)  참고해보시기 바랍니다.

### 디버깅 콘솔에서 확인하기

DAMDA Console 혹은 DAMDA 기기에서 디버깅 콘솔을 실행합니다.&#x20;

디버깅 콘솔의 요약 페이지에 마지막 배포에 관한 정보가 나옵니다. 배포상태가 COMPLETED 이면 배포가 완료된 것입니다.

디버깅 콘솔에 관한 자세한 내용은 [debugging-console.md](../../damda-device/debugging-console.md "mention") 참조해주세요

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### index.html 확인하기

DAMDA 기기에서 DAMDA Home을 실행합니다.

![](../../../.gitbook/assets/image.png)

Home에서는 설치된 sample앱과 내 컴포넌트의 목록을 확인할 수 있습니다.&#x20;

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

내 컴포넌트 배포가 정상적으로 완료 되었다면, home을 실행했을 때 배포한 앱을 볼 수 있습니다. 이 때, 배포한 것이 index.html을 포함하는 앱이라면, 앱 아이콘을 눌러 해당 앱의 index.html 페이지로 이동할 수 있습니다.\
index.html을 포함하는 앱에 관한 설명은 [[develop-component-code.md](develop-component-code.md "mention")](develop-component-code.md#home)를 참고해주시기 바랍니다.



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
  "{root}/zip파일명/코드파일경로" 로 작성되어야 합니다. [컴포넌트 배포 따라하기](../../../quick-start/hello-damda.md#3.-zip-damda)에서 간단한 예제를 확인할 수 있습니다.
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
