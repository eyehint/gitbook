# DAMDA Debugging Console

## 실행방법

### DAMDA Console을 통해서 실행하기

`DAMDA Console -> 디바이스 탭 -> 배포한 디바이스 ID 오른쪽에 detail 클릭 -> 디버깅 콘솔 버튼을 클릭`하여 디버깅 콘솔에 접속할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

#### 주의사항

디버깅 콘솔을 사용하기 위해서는 damda 사이트 설정에서 <mark style="color:red;">안전하지 않은 컨텐츠 허용</mark>을 해주셔야 합니다.

<figure><img src="../../.gitbook/assets/image (10) (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1) (8).png" alt=""><figcaption></figcaption></figure>



### 라즈베리파이에서 실행하기

라즈베리파이에서 `메뉴 -> 기타 -> DAMDA Debugging Console` 을 클릭하여 접속할 수 있습니다. 혹은 라즈베리파이에서 브라우저를 직접실행하여 localhost:8787로도 접속할 수 있습니다.

![](<../../.gitbook/assets/image (34) (1).png>)



## 디버깅 콘솔 사용하기

### 기기 상태 요약정보

코어 디바이스의 정보, 배포상태, 로그 등을 전반적인 정보를 간략하게 볼 수 있습니다.

<figure><img src="../../.gitbook/assets/image (4) (4).png" alt=""><figcaption><p>기기 정보 요약</p></figcaption></figure>

### 컴포넌트 로그 모니터링

컴포넌트가 배포, 설치, 실행, 되는 과정을 모니터링 할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption><p>컴포넌트 별 배포 로그 (실행 스크립트 로그 포함)</p></figcaption></figure>

### 유저 생성 로그 모니터

유저가 /var/log/damda 안에 남긴 로그를 모니터링 할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (1) (1) (5).png" alt=""><figcaption><p>컴포넌트 별 사용자 로그</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (7) (2) (1).png" alt=""><figcaption><p>'QuickStart > 내컴포넌트 로그 확인하기'의 로그 예시</p></figcaption></figure>

### 네트워크 리소스 모니터

현재 사용중인 포트의 정보를 모니터링 할 수 있습니다.

<figure><img src="../../.gitbook/assets/image (6) (2) (1).png" alt=""><figcaption><p>사용중인 포트 번호 목록</p></figcaption></figure>

## 이슈 전송

이슈 전송 메뉴를 통하여 damda-admin에 버그 리포트를 할 수 있습니다. 자동으로 시스템 로그가 함 전송됩니다.

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption><p>이슈 전송 페이지</p></figcaption></figure>

## 사용 예제 동영상

아래는 Damda Debugging Tool 작동 예제 동영상 입니다.&#x20;

{% embed url="https://youtu.be/RfuPn4IFaT4" %}
