---
description: DAMDA제품을 ThinQ에 등록하여 ThinQ앱과 연동합니다.
---

# ThinQ 연결하기

## 1. ThinQ 제품으로 등록하기

라즈베리파이에서 **DAMDA Home 앱**을 실행 시킵니다.&#x20;

![](<../.gitbook/assets/image (5).png>)

Home 에서 **'ThinQ에 내 제품으로 등록하기**'를 클릭합니다.&#x20;

<figure><img src="../.gitbook/assets/image (81).png" alt=""><figcaption><p>DAMDA Home 첫 화면</p></figcaption></figure>

ThinQ 로그인을 할 수 있는 앱이 실행되어 Pin/QR코드가 화면에 보입니다.

<figure><img src="../.gitbook/assets/image (106).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
생성된 Pin/QR 코드는 **60초 동안**만 유효합니다. 시간이 지난 경우 '**갱신**' 버튼을 통해 새로 발급을 받아야 사용이 가능합니다.
{% endhint %}

스마트폰에서 사용하려는 계정을 가진 **LG ThinQ App**을 실행 시킵니다.&#x20;

**'설정' > 'ThinQ 계정 공유'** 메뉴를 선택하고 앱에서 제공하는 Pin 코드 또는 QR 코드 로그인을 진행합니다.&#x20;

<figure><img src="../.gitbook/assets/image (122).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
ThinQ 계정 정보가 DAMDA 기기로 전달되어 자동으로 DMADA 기기가 ThinQ 서버에 등록되는 과정이 진행됩니다.&#x20;
{% endhint %}

## &#x20;2. LG ThinQ 앱에서 등록 기기 확인하기

DAMDA 기기가 정상적으로 등록이 완료되면 해당 기기 정보를 LG ThinQ 앱에서 확인할 수 있습니다.&#x20;

본인의 LG ThinQ 앱 화면에 아래와 같이 "**DAMDA 제품**" 카드가 정상적으로 나타나는지 확인해 보세요

<img src="../.gitbook/assets/image (174).png" alt="" data-size="original">

## 3. ThinQ 연동 샘플 컴포넌트 배포하기 (Control app)

{% hint style="info" %}
Control App 예제는 라즈베리파이의 GPIO를 제어하는 예제입니다. \
별도의 센서를 연결 하시면 실제 동작까지 확인해 보실 수 있습니다.&#x20;
{% endhint %}

**Step 1.** 다음과 같이 Control App 코드(nodejs)를 작성합니다. (index.js)

```javascript
var ws = require('ws');
const Gpio = require('onoff').Gpio;
const led = new Gpio(21, 'out');

var socket = new ws("ws://localhost:8951/com.damda.sample.control_app/control");

socket.on("open", function(){
    console.log("connected");
});

socket.on("error", function(err){
   console.log("error: ", err);
});

socket.on("close", function(){
   console.log("close");
});

socket.on("message", function(data){
   console.log("data: ", data.toString());
   data = JSON.parse(data.toString());
   if (data["command"] == "ledon") {
       console.log("ledon is called")
        led.writeSync(1);
   } else if (data["command"] == "ledoff"){
       console.log("ledoff is called")
       led.writeSync(0);
   }
});
```

**Step 2.** 필요한 node module을 설치합니다.&#x20;

```
$ npm install ws
$ npm install onoff
```

**Step 3.** component 파일을 압축합니다.&#x20;

```
$ ls
index.js
$ zip -r control_app.zip index.js
```

{% hint style="info" %}
control\_app.zip의 구조는 다음과 같습니다.&#x20;

control\_app.zip\
ㄴ index.js
{% endhint %}

{% hint style="info" %}
위 과정이 적용된 예제 파일은 [control-app.md](../reference/samples/control-app.md "mention")에서 다운로드 가능합니다.
{% endhint %}

**Step 4.** DAMDA Console([https://damda.lge.com/](https://damda.lge.com))에 접속하여 Component를 등록합니다.

<figure><img src="../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
컴포넌트 이름을 com.damda.sample.control\_app 으로 작성해야 합니다.&#x20;

컴포넌트의 이름을 변경하시면 Step 1 코드 내 웹 소켓 연결부분의 수정이 필요합니다.
{% endhint %}

**Step 5**. 압축파일 (control\_app.zip)을 코드에 등록하고 실행 스크립트를 다음과 같이 등록합니다.&#x20;

```
npm install ws --prefix {root}/control_app/.
```

```
npm install onoff --prefix {root}/control_app/.
```

```shell
node {root}/control_app/index.js
```

마지막으로 requirePrivilege를 true로 설정하고 Component를 저장합니다.&#x20;

<figure><img src="../.gitbook/assets/image (111).png" alt=""><figcaption></figcaption></figure>

****

**Step 6**. 등록된 내 컴포넌트(com.damda.sample.control\_app)를 배포하기를 통하여 내 기기로 배포합니다.&#x20;

{% hint style="danger" %}
퍼블릭 컴포넌트 중 com.damda.public.hub 를 제외할 경우 정상 동작하지 않을 수 있습니다.\
반드시 포함하여 배포하여 주시기 바랍니다.&#x20;
{% endhint %}

<figure><img src="../.gitbook/assets/image (110).png" alt=""><figcaption></figcaption></figure>

\[Optional] 디버깅 콘솔에 다음과 같은 화면이 나타나면 정상적으로 배포된 것임을 확인할 수 있습니다. \
([undefined-1.md](undefined-1.md "mention")를 참고하세요)





## 4. ThinQ 연동 샘플 TPA 설치하기 (Control App 제어)

업데이트 예정입다. &#x20;

TPA 개발 가이드는 [https://thinqapp.developer.lge.com/ko/documentation/get-started/tpa-quick-start/](https://thinqapp.developer.lge.com/ko/documentation/get-started/tpa-quick-start/) 를 참고해주세요

## 5. ThinQ 연동 샘플 실행결과

업데이트 예정입니다. &#x20;
