---
description: 컴포넌트 타입별 개발 가이드입니다
---

# 컴포넌트 개발하기

## Home에서 직접 실행할 수 있는 컴포넌트 작성 방법

컴포넌트 코드의 가장 상위 경로에 index.html을 추가합니다. Home에서 앱(컴포넌트)의 아이콘을 클릭하면 정의한 index.html 페이지를 실행합니다. 예시로 [Hello Damda](../../../quick-start/hello-damda.md)를 참고할 수 있습니다.

이때 <mark style="color:red;">**zip파일명과 컴포넌트 명의 suffix와 반드시 동일**</mark>해야합니다.

예를 들어, 컴포넌트명이 **com.damda.sample.hellodamda** 이면 zip파일은 **hellodamda.zip**로 만들어야 합니다. 다른이름으로 zip파일을 생성할 경우, index.html이 인식되지 않습니다.

| 종류     | 추가 방법                                                                                                                                                                                                                                                          |
| ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 시작 페이지 | zip파일 안에 index.html을 포함시킵니다.                                                                                                                                                                                                                                   |
| 앱 아이콘  | zip파일 안에 icon.png을 포함시킵니다. index.html과 같은 위치에 두어야 인식됩니다.                                                                                                                                                                                                       |
| 앱 이름   | <p>컴포넌트 생성 시 TAG에 AppName을 key로 하여 이름을 추가해줍니다.</p><p></p><p>AppName을 포함하지 않은 컴포넌트는, 컴포넌트명의 마지막 부분을 이름으로 사용하게 됩니다. 예를 들어, 이름이 com.damda.sample.hellodamda라면, hellodamda가  앱 이름으로 사용됩니다.</p><p><br><img src="../../../.gitbook/assets/image (4).png" alt=""></p> |

## Frontend와 Backend를 분리해서 개발하는 컴포넌트

업데이트 예정입니다.

## Python 컴포넌트 스크립트 참고사항

업데이트 예정입니다.

## Nodejs 컴포넌트 스크립트 참고사항

추가로 필요한 패키지가 있는 경우, 라즈베리파이 환경에 맞는 node module 만들어 줍니다.&#x20;

node module을 포함하여 zip파일로 압축 한 후 배포합니다.&#x20;

{% hint style="danger" %}
주의: 실행스크립트에 npm install을 사용하면 첫 배포만 정상적으로 진행되고 다음 배포부터는 배포 오류가 발생합니다&#x20;
{% endhint %}

React, Vue등 Front End Webapp 배포시 build된 정적 파일을 배포하여 npx http-server로 실행하는 것을 권장합니다.
