# 컴포넌트 생성하기

## 컴포넌트 정보&#x20;



![](<../../../.gitbook/assets/image (2) (6).png>)                  ![](<../../../.gitbook/assets/image (2).png>)

#### **컴포넌트 명 (필수)**

<mark style="color:red;">com.\[damda계정].\[컴포넌트명]</mark> 으로 정의합니다 컴포넌트명이 중복되는 경우 생성할 수 없습니다.&#x20;

**설명 (필수)**

어떤 컴포넌트인지 간략한 설명을 적어줍니다. 필수로 입력해야 합니다.

#### **태그**&#x20;

컴포넌트의 기타 정보를 태그로 추가해서 관리할 수 있습니다. 필요하지 않다면 비워두도 좋습니다.

#### **코드 (필수)**

zip파일로 올립니다. 이때 zip 파일명을 기준으로 실행스크립트 경로를 작성하게 됩니다.

{% code title="app.py 실행 스크립트 예시 " %}
```
python {root}/zip파일명 app.py 
```
{% endcode %}

#### **환경 변수**

컴포넌트가 실행될 때 사용할 환경 변수를 정의합니다.

#### **실행 스크립트**

실행 스크립트는 4가지 종류가 있습니다. 초기 설정, 설치, 실행, 종료 입니다.

{% tabs %}
{% tab title="초기 설정" %}
다음과 같은 경우에 실행됨

* 컴포넌트가 코어 디바이스에 처음 배포 될 때
* 컴포넌트의 버전이 바뀌었을때
* 컴포넌트의 설정 업데이트로 bootstrap 스크립트가 바뀌었을때
* GGC s/w가 재시작되거나 코어 디바이스가 재시작 될 때 실행

다음과 같은 항목을 포함할 수 있음

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
다음과 같은 경우에 실행됨

* 컴포넌트를 설치할때 실행
* GGC s/w가 실행 (launch)될 때 마다 실행

다음과 같은 항목을 포함할 수 있음

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
다음과 같은 경우에 실행됨

* 컴포넌트가 시작 될 때 실행

다음과 같은 항목을 포함할 수 있음

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
다음과 같은 경우에 실행됨

* 컴포넌트를 내릴 때 실행 (shut down)

다음과 같은 항목을 포함할 수 있음

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

각 스크립트에 '**작성**' 버튼을 누르면 스크립트의 세부내용을 설정하는 창이 나타납니다.

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Script의 '**+**'를 누르면 스크립트를 입력할 수 있는 칸이 생성됩니다. 이 때, 스크립트는 **한칸에 하나의 command만** 입력해야 합니다.&#x20;

![](../../../.gitbook/assets/image.png)\




### Python 컴포넌트 스크립트 참고사&#x20;

### Nodejs 컴포넌트 스크립트 참고사항

## TroubleShooting

<details>

<summary><strong>ValidationExcption</strong> 발생</summary>

****![](<../../../.gitbook/assets/image (2) (2).png>)****

코드 파일이 업로드 중인 경우 ValidationException 이 발생할 수 있습니다 잠시 기다렸다가 다시 저장버튼을 눌러주세요

</details>

<details>

<summary>"일한 버전이 존재합니다" 에러 발생</summary>

컴포넌트 생성 시, 같은 이름을 가진 컴포넌트가 존재하는 경우 "동일한 버전이 존재합니다"라는 에러가 발생 합니다.

기존에 만든 컴포넌트에 새로운 버전을 추가 할때도 버전을 잘 못입력하면 "동일한 버전이 존재합니다"라는 에러가 발생할 수 있습니다.

<img src="../../../.gitbook/assets/image (15) (1).png" alt="" data-size="original">

</details>



