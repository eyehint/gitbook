---
description: 가전 API를 활용한 샘플코드 입니다.
---

# 가전 App



### Prerequisites

* [node](https://nodejs.org/ko/)
* npm : node 설치시 자동으로 설치됨
* [vue-cil](https://cli.vuejs.org/guide/installation.html)
* ThinQ 엡에서 실기기 등록 or ThinQ Simulator([https://simulator.lgthinq.com/](https://simulator.lgthinq.com/)) 가상기기 등록 (LG Account, KR)



### Dependency

아래 public component를 사용하는 컴포넌트 입니다.

* [com.damda.thinq-backend-api](https://docs.damda.lge.com/reference/api-reference/api/undefined)



### 웹 애플리케이션 로컬에서 실행

◎ 로컬에서의 실행은 코드가 정상인지 확인하는 용도이며 백엔드 연동이 안되어 프로그램이 정상적으로 동작하지는 않습니다.

{% file src="../../.gitbook/assets/thinq-web-front-example.zip" %}
샘플 코
{% endfile %}

1. 상단의 샘플 코드 다운로드
2. 압축 해제 후 터미널에서 다음 명령 실행
   * ```
     npm install
     npm run build
     ```
3. [http://localhost:9001](http://localhost:9001/) 로 접속하여 로그인 페이지 확인



### 웹 애플리케이션 Damda 컴포넌트로 실행

**컴포넌트 생성**

{% file src="../../.gitbook/assets/thinq-web-front-example.zip" %}
샘플 코드
{% endfile %}

1. 상단의 샘플 코드 다운로드
2. 압축 해제 후 터미널에서 다음 명령 실행
   * ```
     npm install
     npm run build
     ```
3. [http://localhost:9001](http://localhost:9001/) 로 접속하여 로그인 페이지 확인
4.  빌드된 웹 어플리케이션 파일 압축하기 (thinqweb.zip)

    빌드된 dist 폴더의 모든 파일을 압축합니다

    * dist/\*
5. [DAMDA console](https://damda.lge.com/) 로그인 > 컴포넌트 > 컴포넌트 추가
   * 컴포넌트 생성을 위해 필요한 정보를 넣어 줍니다.
   * 컴포넌트명 : "com.damda.sample.thinqweb-example" 입력\
     \- Unique한 이름을 지정해야 함. damda 플랫폼 내 중복되는 이름의 컴포넌트가 존재하는 경우 컴포넌트 생성 불가\
     \- 컴포넌트명 추천 형식 : com.<개인 식별 키워드>.sample.thinqweb-example
   * 설명 : ‘Thinq web front 예제’ 입력
   * 코드 : '3. 예제 코드 파일 압축' 단계에서 생성한 'thinqweb.zip' 파일 업로드
   * 실행 스크립트 : 코드가 디바이스에 설치 후 실행하기 위해 필요한 스크립트 작성
   * ```
     npx http-server {root}/dist -p 9019
     ```
   * 홈 화면 출력' 체크
   * 썸네일 이미지 : 자유롭게 선택
   * 앱 이름 : 'ThinqWeb예제' 입력
   * 접속 링크 : 'http://127.0.0.1:9019' 입력\
     \- 홈 화면에서 썸네일 클릭 시 이동할 링크 주소
6.  컴포넌트 생성 완료

    <figure><img src="https://developer.damda.lge.com/assets/img/example3-2.png" alt=""><figcaption></figcaption></figure>

**컴포넌트 배포**

1.  배포할 컴포넌트를 모두 선택 > 배포하기 (public 컴포넌트는 기본적으로 모두 배포 리스트에 추가됨)

    <figure><img src="https://developer.damda.lge.com/assets/img/example3-3.png" alt=""><figcaption></figcaption></figure>
2. 배포할 컴포넌트 리스트를 확인 > 배포할 "코어 디바이스 선택" > 배포요청![](https://developer.damda.lge.com/assets/img/example3-4.png)

**컴포넌트 실행 확인**

1. 배포 완료 후 라즈베리파이에서 "[http://localhost:8002](http://localhost:8002)" 접속
2.  다음과 같이 홈 화면에 위에서 배포한 ThinQ web front 예제 컴포넌트가 보이는 것을 확인합니다.\


    <figure><img src="https://developer.damda.lge.com/assets/img/example3-5.png" alt=""><figcaption></figcaption></figure>
3. 아이콘을 클릭하여 배포한 컴포넌트 웹 애플리케이션 실행
4.  웹 페이지에 연결되면 lg account 로그인 후 가전 상태조회 및 컨트롤을 테스트 할 수 있습니다.\
    ※ 기기 상태(Event) 및 PUSH를 확인하기 위해서는 Subscribe Event/Push 버튼을 클릭하여야 합니다.\


    <figure><img src="https://developer.damda.lge.com/assets/img/example3-6.png" alt=""><figcaption></figcaption></figure>

