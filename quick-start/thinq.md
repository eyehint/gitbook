---
description: DAMDA제품을 ThinQ에 등록하여 ThinQ앱과 연동합니다.
---

# ThinQ 연결하기

## 1. ThinQ 제품으로 등록하기

라즈베리파이에서 **DAMDA Home 앱**을 실행 시킵니다.&#x20;

![](<../.gitbook/assets/image (16).png>)

Home 에서 **'ThinQ에 내 제품으로 등록하기**'를 클릭합니다.&#x20;

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

ThinQ 로그인을 할 수 있는 앱이 실행되어 Pin/QR코드가 화면에 보입니다.

<figure><img src="../.gitbook/assets/image (1) (3) (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
생성된 Pin/QR 코드는 **60초 동안**만 유효합니다. 시간이 지난 경우 '**갱신**' 버튼을 통해 새로 발급을 받아야 사용이 가능합니다.
{% endhint %}

스마트폰에서 사용하려는 계정을 가진 **LG ThinQ App**을 실행 시킵니다.&#x20;

**'설정' > 'ThinQ 계정 공유'** 메뉴를 선택하고 앱에서 제공하는 Pin 코드 또는 QR 코드 로그인을 진행합니다.&#x20;

<figure><img src="../.gitbook/assets/image (11) (2) (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
ThinQ 계정 정보가 DAMDA 기기로 전달되어 자동으로 DMADA 기기가 ThinQ 서버에 등록되는 과정이 진행됩니다.&#x20;
{% endhint %}

## &#x20;2. LG ThinQ 앱에서 등록 기기 확인하기

DAMDA 기기가 정상적으로 등록이 완료되면 해당 기기 정보를 LG ThinQ 앱에서 확인할 수 있습니다.&#x20;

본인의 LG ThinQ 앱 화면에 아래와 같이 "**DAMDA 제품**" 카드가 정상적으로 나타나는지 확인해 보세요

<img src="../.gitbook/assets/image (4) (6).png" alt="" data-size="original">



## 3. ThinQ 연동 샘플 컴포넌트 배포하기 (Control app)

{% hint style="info" %}
Control App 예제는 라즈베리파이의 GPIO를 제어하는 예제입니다. \
별도의 센서를 연결 하시면 실제 동작까지 확인해 보실 수 있습니다.&#x20;
{% endhint %}

**Step 1.** 다음과 같이 Control App 코드(nodejs)를 작성합니다. (index.js)

```javascript
var mqtt = require('mqtt');
var request = require('request');
const Gpio = require('onoff').Gpio;
const led = new Gpio(21, 'out');

options = {
    host:"localhost",
    port:1883,
    protocol:'mqtt'
}

const client = mqtt.connect("localhost", options);
http_options = {
	uri : "localhost:8951",
	path : "/monitoring",
	method : "POST",
	json:true
}

client.on("connect", ()=> {
        console.log("Connected" + client.connected);
    }
);

client.on("error", (error) => {
  console.log("Can't connect" + error);
});

client.subscribe("damda/control", function(){
	console.log("subscribed");
});

client.on("message", (topic, message, packet) => {
	console.log("message is ", message.toString());
	console.log("topic is ", topic);
	data = JSON.parse(message.toString());   
	if (data["command"] == "ledon") {
		console.log("ledon is called")
		led.writeSync(1);
		body = 
			{ "monitoring" : 
				{ "component" : "com.damda.sample.control_app", 
				  "led" : "ON"
				}
			}
		
	} else if (data["command"] == "ledoff"){
		console.log("ledoff is called")
		led.writeSync(0);   
		body = 
			{ "monitoring" : 
				{ "component" : "com.damda.sample.control_app", 
				  "led" : "OFF"
				}
			}

	}
	req = request.post({
		"url":"http://localhost:8951/monitoring", 
		"body": JSON.stringify(body)
		},  
		function(err, res, body){
			console.log(res);
	});
});

```

**Step 2.** component 파일을 압축합니다.&#x20;

```
$ ls
index.js 
$ zip -r control_app.zip index.js
```

{% hint style="info" %}
control\_app.zip의 구조는 다음과 같습니다.&#x20;

control\_app.zip\
ㄴ index.js&#x20;
{% endhint %}

{% hint style="info" %}
위 과정이 적용된 예제 파일은 [control-app.md](../reference/samples/control-app.md "mention")에서 다운로드 가능합니다.
{% endhint %}

**Step 3.** DAMDA Console([https://damda.lge.com/](https://damda.lge.com))에 접속하여 Component를 등록합니다.

<figure><img src="../.gitbook/assets/image (6) (5).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
컴포넌트 이름을 com.<계정명>.sample.control\_app 으로 작성해야 component 충돌이 나지 않습니다.&#x20;
{% endhint %}

**Step 4**. 압축파일 (control\_app.zip)을 코드에 등록하고 실행 스크립트를 다음과 같이 등록합니다.&#x20;

```
npm install mqtt --prefix {root}/control_app/.
```

```
npm install onoff --prefix {root}/control_app/.
```

```
npm install request --prefix {root}/control_app/.
```

```shell
node {root}/control_app/index.js
```

마지막으로 requirePrivilege를 true로 설정하고 Component를 저장합니다.&#x20;

<figure><img src="../.gitbook/assets/image (2) (7).png" alt=""><figcaption></figcaption></figure>

**Step 5**. 등록된 내 컴포넌트(com.<계정>.sample.control\_app)를 배포하기를 통하여 내 기기로 배포합니다.&#x20;

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

## 4. ThinQ 연동 샘플 TPA 설치하기 (Control App 제어)

TPA 개발 환경 설정은 [https://thinqapp.developer.lge.com/ko/documentation/get-started/tpa-quick-start/](https://thinqapp.developer.lge.com/ko/documentation/get-started/tpa-quick-start/) 를 참고해주세요 (helloworld 출력까지 진행이 필요합니다)

{% hint style="info" %}
TPA를 사용하기 위해서는 ThinQ앱 설정을 변경하여야 합니다. 자세한 가이드는 아래 링크를 확인해주세요.

[https://thinqapp.developer.lge.com/index.php/ko/documentation/development/ihm-development/ihm\_development\_guide/](https://thinqapp.developer.lge.com/index.php/ko/documentation/development/ihm-development/ihm\_development\_guide/)
{% endhint %}

**Step 1.** visual studio 내 EXA 폴더를 아래 파일의 압축을 풀어서 덮어써줍니다.&#x20;

{% file src="../.gitbook/assets/EXA_221025.zip" %}

![](<../.gitbook/assets/image (5).png>)

**Step 2.** DAMDA ThinQ Agent API (GET http://{device IP}/device )를 이용하여 기기의 Device ID를 확인합니다.&#x20;

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Step 3. _`interface/dashBoardCardInterface.js`_ 파일의 11번째 줄에 있는 device id 값을 자신의 device id 값으로 바꿔줍니다.&#x20;

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

**Step 4.** Terminal을 통해 EXA 모듈을 실행합니다.&#x20;

```
npm run thinq_tpa -- DoB -n EXA
```

**Step 5.** ThinQ App을 통해 EXA 모듈이 정상적으로 실행이 되는지 확인합니다. (ThinQ App과 TPA 모듈은 동일 네트워크에 있어야 합니다)

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## 5. ThinQ 연동 샘플 실행결과



{% embed url="http://10.178.133.16/poc/3.thinq.mp4" %}
