---
description: 가전 API를 활용한 샘플코드 입니다.
---

# 가전 App

### Prerequisites

* [node](https://nodejs.org/ko/)
* npm : node 설치시 자동으로 설치됨
* [vue-cil](https://cli.vuejs.org/guide/installation.html)
* ThinQ 에서 실기기 등록 or ThinQ Simulator([https://simulator.lgthinq.com/](https://simulator.lgthinq.com/)) 가상기기 등록 (LG Account, KR)



### Dependency

아래 public component를 사용하는 컴포넌트 입니다.

* [com.damda.thinq-backend-api](../api-reference/api/undefined.md)



### 웹 애플리케이션 로컬에서 실행

◎ 로컬에서의 실행은 코드가 정상인지 확인하는 용도이며 백엔드 연동이 안되어 프로그램이 정상적으로 동작하지는 않습니다.

{% file src="../../.gitbook/assets/thinq-web-front-example.zip" %}

1. 상단의 샘플 코드 다운로드
2.  /src/views 폴더 내 Device.vue, Login.vue의 코드 수정

    1. Device  vue:  ThinQ Connect Key
    2. Login.vue: EMP Key             &#x20;

    ```javascript
    ...
    </template>

    <script>
    ...
    const clientId = 발급 받은 client_id 입력
    const clientSecret = 발급 client_secret 입
    ```
3. &#x20;                                                                          q
4.  압축 해제 후 터미널에서 다음 명령 실행

    ```
    npm install
    npm run build
    ```
5. [http://localhost:9001](http://localhost:9001/) 로 접속하여 로그인 페이지 확인



### 웹 애플리케이션 Damda 컴포넌트로 실행

**컴포넌트 생성**

{% file src="../../.gitbook/assets/thinq-web-front-example.zip" %}

1. 상단의 샘플 코드 다운로드
2.  /src/views 폴더 내 Device.vue, Login.vue의 코드 수정

    ```javascript
    ...
    </template>

    <script>
    ...
    const clientId = 발급 받은 client_id 입력
    const clientSecret = 발급 client_secret 입
    ```
3.  압축 해제 후 터미널에서 다음 명령 실행

    ```
    npm install
    npm run buil
    ```
4. [http://localhost:9001](http://localhost:9001/) 로 접속하여 로그인 페이지 확인
5.  빌드된 웹 어플리케이션 파일 압축하기 (thinqweb.zip)

    빌드된 dist 폴더의 모든 파일을 압축합니다

    * dist/\*
6.  DAMDA Console([http://damda.lge.com](http://damda.lge.com/))에 접속하고 본인의 계정을 이용하여 로그인을 합니다.

    <figure><img src="https://92628155-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fvgd5fM997o3xx0yyghJF%2Fuploads%2FdHk0ezB9jUx2vUSUhfGu%2Fimage.png?alt=media&#x26;token=0b1569a8-65d1-4846-a93c-1122c7c7bb40" alt=""><figcaption></figcaption></figure>
7.  좌측 메뉴의 '**컴포넌트**'를 선택하여 컴포넌트 화면으로 진입합니다.

    <figure><img src="https://92628155-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fvgd5fM997o3xx0yyghJF%2Fuploads%2FDnj4ImNtHxIbr3I9ulra%2Fimage.png?alt=media&#x26;token=35f4b376-e8e6-459a-bf70-f0b92b2880f7" alt=""><figcaption></figcaption></figure>
8.  '**컴포넌트 생성**' 버튼을 클릭하면 컴포넌트 생성 팝업이 나타납니다.

    <figure><img src="https://92628155-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fvgd5fM997o3xx0yyghJF%2Fuploads%2F2dV4vKkuOQWhZeDPu1Cd%2Fimage.png?alt=media&#x26;token=381c392b-9bb9-4af9-b430-e55368d42915" alt=""><figcaption></figcaption></figure>
9.  **컴포넌트명**과 **설명**을 입하고 '**다음**' 버튼을 클릭하여 컴포넌트 추가 설정 화면으로 이동합니다.

    <figure><img src="https://92628155-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fvgd5fM997o3xx0yyghJF%2Fuploads%2F7mf3OXtEQiHWiFMtF6AC%2Fimage.png?alt=media&#x26;token=78f88ad5-cb95-4c68-a43a-7e45ba5ac77f" alt=""><figcaption></figcaption></figure>

    * **컴포넌트명** : "com.damda.sample.thinqweb-example" 입력\
      \- Unique한 이름을 지정해야 함. damda 플랫폼 내 중복되는 이름의 컴포넌트가 존재하는 경우 컴포넌트 생성 불가\
      \- 컴포넌트명 추천 형식 : com.<개인 식별 키워드>.sample.thinqweb-example
    * **설명** : ‘Thinq web front 예제’ 입력
10. '**코드**' 항목의 '**추가**' 버튼을 이용하여 4단계에서 압축해둔 파일을 업로드합니다.
11. '**실행 스크립트**' 항목의 '**작성**' 버튼을 이용하여 실행 단계에서 사용할 실행 스크립트를 작성합니다.

    <figure><img src="../../.gitbook/assets/스크린샷 2022-10-14 오후 2.44.50 (1).png" alt=""><figcaption></figcaption></figure>

    * **Script** : 코드가 디바이스에 설치 후 '**실행'** 단계에서 실행될 스크립트
    * ```
      npx http-server {root}/dist -p 9019
      ```
12. 컴포넌트 생성 완료

    <figure><img src="https://developer.damda.lge.com/assets/img/example3-2.png" alt=""><figcaption></figcaption></figure>

****

**컴포넌트 배포**

1.  배포할 컴포넌트를 모두 선택 > 배포하기 (public 컴포넌트는 기본적으로 모두 배포 리스트에 추가됨)

    <figure><img src="https://developer.damda.lge.com/assets/img/example3-3.png" alt=""><figcaption></figcaption></figure>
2.  배포할 컴포넌트 리스트를 확인 > 배포할 "코어 디바이스 선택" > 배포요청

    <figure><img src="https://developer.damda.lge.com/assets/img/example3-4.png" alt=""><figcaption></figcaption></figure>

****

**컴포넌트 실행 확인**

1. 배포 완료 후 라즈베리파이에서 "[http://localhost:9019](http://localhost:9019)" 접속
2.  다음과 같이 웹 페이지에 연결되면 lg account 로그인 후 가전 상태조회 및 컨트롤을 테스트 할 수 있습니다.\
    ※ 기기 상태(Event) 및 PUSH를 확인하기 위해서는 Subscribe Event/Push 버튼을 클릭하여야 합니다.\


    <figure><img src="https://developer.damda.lge.com/assets/img/example3-6.png" alt=""><figcaption></figcaption></figure>

