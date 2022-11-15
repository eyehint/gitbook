# 컴포넌트 초기화하기

사용자가 설치했던 커스텀 컴포넌트들을 삭제하고, damda 기기를 초기상태([Quick Start 1단계:개발환경구성](../../../quick-start/setup-env.md)이 완료된 상태)로 초기화 하는 방법입니다.

## How to do

1. 컴포넌트를 선택하지 않고 배포하기를 누릅니다. \
   혹은 배포작업 생성 팝업에서 추가되어있는 모든 컴포넌트들을 "제외"시켜줍니다.
2. 배포에 포함된 컴포넌트가 없이 "배포요청"을 진행하면 "기기초기화"를 묻는 팝업이 나타나게 됩니다
3. "예"를 눌러 초기화 배포를 진행합니다.

<figure><img src="../../../.gitbook/assets/image (31).png" alt=""><figcaption><p>기기 초기화 진행 여부 팝업</p></figcaption></figure>

{% hint style="warning" %}
만약 기기 전반적인 설정에 문제가 생긴경우, 배포 실패가 발생할 수 있습니다. 이 경우 damda uninstall 후 다시 install을 진행해주시기 바랍니다.
{% endhint %}
