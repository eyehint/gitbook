---
description: 컴포넌트 생성 창에서 입력해야 하는 각 항목에 대한 가이드 페이지 입니다.
---

# 컴포넌트 생성하기

## 컴포넌트 정보 입력&#x20;

[Damda Console](http://damda.lge.com/)에서 "컴포넌트 생성" 버튼을 클릭하여 컴포넌트 만들수 있습니다. 컴포넌트 생성에 필요한 정보들을 입력합니다.

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
사전에 컴포넌트로 만들 코드를 zip파일로 묶어 준비합니다. 압축파일을 풀었을 때, '압축파일명/' 밑에 코드 파일이 생성되도록 압축해야합니다.&#x20;

예를들어 hellodamda.zip 압축을 해제하면 아래와 같이 구성하는 컴포넌트를 구성하는 파일들이 바로 보여야 합니다.&#x20;

![](<../../../.gitbook/assets/image (2).png>)
{% endhint %}

### 컴포넌트 기본 정보 설정

![](<../../../.gitbook/assets/image (2) (6).png>)                  ![](<../../../.gitbook/assets/image (2) (5).png>)

#### ****

#### **컴포넌트 명 (필수)**

<mark style="color:red;">com.\[damda계정].\[컴포넌트명]</mark> 으로 정의합니다 컴포넌트명이 중복되는 경우 생성할 수 없습니다.&#x20;

계정이 <mark style="color:green;background-color:orange;"><mark style="background-color:orange;">damda.user@lge.com<mark style="background-color:orange;"></mark>이고 <mark style="color:green;"></mark> <mark style="background-color:orange;">hellodamda</mark>라는 컴포넌트를 만들고 싶은 경우, <mark style="background-color:orange;">com.damda.user.hellodamda</mark> 라고 컴포넌트 명을 입력합니다.

{% hint style="warning" %}
규칙에 맞지 않는 컴포넌트 명을 사용할 수도 있습니다. 다만, 이 경우 damda 시스템 내에 중복되는 이름이 존재해서, 컴포넌트가 정상적으로 생성되지 않을 수 있습니다.&#x20;

위와 같은 형식으로 컴포넌트 명을 작성하시길 권장합니다.
{% endhint %}

**설명 (필수)**

어떤 컴포넌트인지 간략한 설명을 적어줍니다. 필수로 입력해야 합니다.

#### **태그**&#x20;

컴포넌트의 기타 정보를 태그로 추가해서 관리할 수 있습니다.

#### **코드 (필수)**

zip파일로 올립니다. 이때 zip 파일명을 기준으로 실행스크립트 경로를 작성하게 됩니다.

{% code title="app.py 실행 스크립트 예시 " %}
```
python {root}/zip파일명 app.py 
```
{% endcode %}

{% hint style="info" %}
컴포넌트 버전을 추가할 때마다 zip파일을 다시 업로드 해주어야 합니다.
{% endhint %}

#### **환경 변수**

컴포넌트가 실행될 때 사용할 환경 변수를 정의합니다. 여기서 설정한 환경변수는 모든 lifecycle(초기 설정, 설치, 실행, 종료)에 적용됩니다. port, phase등 실행을 위해 필요한 configuration 정보를 환경 변수로 관리할 때 사용합니다.

#### **실행 스크립트 (**Life cycle 스크립트)

실행스크립트는 컴포넌트의 life cycle 별로 정의합니다. **초기 설정, 설치, 실행, 종료** 4가지 종류가 있습니다.

{% tabs %}
{% tab title="초기 설정" %}
다음과 같은 경우에 실행됩니다.&#x20;

* 컴포넌트가 코어 디바이스에 처음 배포 될 때
* 컴포넌트의 버전이 바뀌었을때
* 컴포넌트의 설정 업데이트로 bootstrap 스크립트가 바뀌었을때
* GGC s/w가 재시작되거나 코어 디바이스가 재시작 될 때 실행

다음과 같은 항목을 포함할 수 있습니다.

* Script: bootstrap에서 실행할 스크립트
* RequiresPrivilege: root 권한으로 실행할지 여부 (default: false)
* Skipif: 스크립트의 실행 여부를 판단
  * onpath runnable: runnable이 있으면 skip
  * exists file: file이 있으면 skip
* Timeout: 스크립트 실행에 대한 타임아웃 (default: 120초)
* Setenv: bootstrap에서만 사용할 환경변수

활용 예시

* 컴포넌트 실행을 위해 필요한 apt install&#x20;
{% endtab %}

{% tab title="설치" %}
다음과 같은 경우에 실행됩니다.

* 컴포넌트를 설치할때 실행
* GGC s/w가 실행 (launch)될 때 마다 실행

다음과 같은 항목을 포함할 수 있습니다.

* Script: install에서 실행할 스크립트
* RequiresPrivilege: root 권한으로 실행할지 여부 (default: false)
* Skipif: 스크립트의 실행 여부를 판단
  * onpath runnable: runnable이 있으면 skip
  * exists file: file이 있으면 skip
* Timeout: 스크립트 실행에 대한 타임아웃 (default: 120초)
* Setenv: install에서만 사용할 환경변수

특징

* 완료 시  컴포넌트 상태가 "INSTALLED"로 됨

활용 예시

* pip3 install이나 컴포넌트 실행을 위해 필요한 configuration 준비
{% endtab %}

{% tab title="실행" %}
다음과 같은 경우에 실행됩니다.

* 컴포넌트가 시작 될 때 실행

다음과 같은 항목을 포함할 수 있습니다.

* Script: run에서 실행할 스크립트
* RequiresPrivilege: root 권한으로 실행할지 여부 (default: false)
* Skipif: 스크립트의 실행 여부를 판단
  * onpath runnable: runnable이 있으면 skip
  * exists file: file이 있으면 skip
* Timeout: 스크립트 실행에 대한 타임아웃, **타임아웃이 없음**
* Setenv: run에서만 사용할 환경변수

특징

* 스크립트 실행 중에는  "RUNNING"로 되고, 완료 시  컴포넌트 상태가 "FINISHED"로 됨
* 타임아웃이 없음
* Startup이나 Run 둘 중 하나만 사용할 수 있음

활용 예시

* 타임아웃이 없기 때문에 서버를 띄우거나 호스팅을 할때 이 스크립트를 활용
* 여러개 서버를 띄우거나 호스팅 할 경우 괄호()로 스크립트를 묶어주고 && 로 여러개 스크립트를 백그라운드(&)로 실행
{% endtab %}

{% tab title="종료" %}
다음과 같은 경우에 실행됩니다.

* 컴포넌트를 내릴 때 실행 (shut down)

다음과 같은 항목을 포함할 수 있습니다.

* Script: shutdown에서 실행할 스크립트
* RequiresPrivilege: root 권한으로 실행할지 여부 (default: false)
* Skipif: 스크립트의 실행 여부를 판단
  * onpath runnable: runnable이 있으면 skip
  * exists file: file이 있으면 skip
* Timeout: 스크립트 실행에 대한 타임아웃 (default: 15초)
* Setenv: shutdown에서만 사용할 환경변수

특징

* 스크립트 실행 중에는  "STOPPING"로 됨
* Startup에서 실행한 백그라운드 프로세스를 내릴때 사용

활용 예시

* MySQL process 내리기 (/etc/init.d/mysqld stop)
{% endtab %}
{% endtabs %}

### Life cycle 상세 설정

각 life cycle 의 '작성' 버튼을 눌러 단계별 세부내용을 설정할 수 있습니다.

<figure><img src="../../../.gitbook/assets/image (10) (1) (2).png" alt=""><figcaption></figcaption></figure>

**환경 변수**

각 life cycle에서 사용될 환경변수를 정의합니다. 이 곳에 선언된 환경변수는, 정의된 life cycle에서만 유효합니다.&#x20;

#### Script

Script 항목에서 '+'를 누르면 스크립트를 입력할 수 있는 칸이 생성됩니다. 여러 줄의 스크립트를 작성하고 싶은 경우, 칸을 추가하며 한 칸당 하나의 스크립트를 입력합니다. 이때 추가한 스크립트들은 컴포넌트 정보 창에서 아래와 같은 형태로 보여지게 됩니다.

```
(스크립트 1) && (스크립트 2) && (스크립트 3)
```

예시로 Debugging Console의 설치 스크립트는 아래와 같이 작성됩니다. 같은 내용을 Debugging Console의 상세화면에서 확인할 수 있습니다. \
![](<../../../.gitbook/assets/image (2) (7).png>) ![](<../../../.gitbook/assets/image (14).png>)

## 컴포넌트 타입 별 Tip

### Home에서 직접 실행할 수 있는 컴포넌트 작성 방법

컴포넌트 코드의 root 경로에 index.html을 추가합니다. Home에서 앱(컴포넌트)의 아이콘을 클릭하면 정의한 index.html 페이지를 실행합니다. 예시로 [Hello Damda](../../../quick-start/step2..md)를 참고할 수 있습니다.

### Frontend와 Backend를 각각의 zip파일로 분리한 컴포넌트

업데이트 예정입니다.

### Python 컴포넌트 스크립트 참고사항

업데이트 예정입니다.

### Nodejs 컴포넌트 스크립트 참고사항

추가로 필요한 패키지가 있는 경우, 라즈베리파이 환경에 맞는 node module 만들어 줍니다.&#x20;

node module을 포함하여 zip파일로 압축 한 후 배포합니다.&#x20;

{% hint style="danger" %}
주의: 실행스크립트에 npm install을 사용하면 첫 배포만 정상적으로 진행되고 다음 배포부터는 배포 오류가 발생합니다&#x20;
{% endhint %}

React, Vue등 Front End Webapp 배포시 build된 정적 파일을 배포하여 npx http-server로 실행하는 것을 권장합니다.

## TroubleShooting

<details>

<summary><strong>ValidationExcption</strong> 발생</summary>

****![](<../../../.gitbook/assets/image (2) (2) (1).png>)****

코드 파일이 업로드 중인 경우 ValidationException 이 발생할 수 있습니다 잠시 기다렸다가 다시 저장버튼을 눌러주세요

</details>

<details>

<summary>"동일한 버전이 존재합니다" 에러 발생 </summary>

컴포넌트 생성 시, 같은 이름을 가진 컴포넌트가 존재하는 경우 "동일한 버전이 존재합니다"라는 에러가 발생 합니다.

기존에 만든 컴포넌트에 새로운 버전을 추가 할때도 버전을 잘 못입력하면 "동일한 버전이 존재합니다"라는 에러가 발생할 수 있습니다.

<img src="../../../.gitbook/assets/image (15) (1) (1).png" alt="" data-size="original">

</details>



