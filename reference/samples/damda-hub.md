---
description: Hub 기능을 사용해볼 수 있는 샘플 예제입니다
---

# DAMDA Hub

**com.damda.sample.damda-hub**를 배포하여 사용할 수 있습니다.&#x20;

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>퍼블릭 컴포넌트 탭에서 damda-hub 샘플앱 확인 가능</p></figcaption></figure>

## 개요

이 샘플앱에서는 서브기기를 등록하고 제어해볼 수 있습니다. 나만의 서브기기 타입을 추가하면, 정의한 기기타입과 허브가 연동되어 동작하는 것을 확인할 수 있습니다. 서브기기 타입을 추가하는 방법은 [custom-sub-device](../../fundamentals/damda-device/custom-sub-device/ "mention")를 확인하시기 바랍니다.

앱 배포 후 Damda Home에 DAMDA Hub가 생성된 것을 확인할 수 있습니다. 아이콘을 눌러, damda-hub의 index.html로 이동합니다.\


## 샘플 코드

damda-hub 코드는 사내용으로 공개합니다. 사내망에서만 다운받으실 수 있습니다.

```shell
curl -O http://10.178.133.16/damda-hub.zip
```

## 컴포넌트 스크립트&#x20;



<details>

<summary>초기 설정</summary>

#### Script&#x20;

```
python3 -m venv /damda/venv/damda-hub)
```

```
docker pull rabbitmq:management
```

```
docker pull redis
```

#### RequiresPrivilege

* true

#### Timeout

* 600

</details>

<details>

<summary>설치</summary>

#### 환경 변수

* VIRTUAL\_ENV&#x20;

#### Script&#x20;

```
docker-compose -f {root}/damda-hub/docker-compose.yml down
```

```
docker-compose -f {root}/damda-hub/docker-compose.yml up -d
```

```
sh {root}/damda-hub/hub-init.sh {root}/damda-hub
```

#### RequiresPrivilege

* true

#### Timeout

* 600

</details>

<details>

<summary><strong>실행</strong></summary>

#### 환경 변수

* VIRTUAL\_ENV&#x20;

#### Script&#x20;

```
	bash {root}/damda-hub/start-hub.sh {root}/damda-hub
```

#### RequiresPrivilege

* true

#### Timeout

* 600

</details>

## DAMDA Hub 사용하기

DAMDA가 허브가 되어 동작합니다.&#x20;

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>DAMDA HUB 첫화면</p></figcaption></figure>

:heavy\_plus\_sign:상단의 "DAMDA HUB"를 클릭하면 앱 테마가 변경됩니다. 맘에 드는 색상으로 사용해 보세요 :sparkles:

### 서브기기 연동하기

허브와 같은 네트워크상에 있는 서브기기들을 연동시켜 볼 수 있습니다. 기본적으로 연동 가능한 기기 타입은 motionCamera, sensorLight, webOSTV, sensorThermoHygrometer 입니다.\
webOSTV를 제외한 나머지 타입들은 시뮬레이터와 연동 하게 됩니다. 시뮬레이터는 해커톤 전에 제공될 예정입니다.&#x20;

{% hint style="warning" %}
현재 시뮬레이터 제공이 늦어지고있어, webOSTV로만 테스트 가능합니다.
{% endhint %}

"추가하기"버튼을 눌러 서브 디바이스의 타입과 연결 하기위한 정보들을 입력합니다.

#### TV 등록하기 예시&#x20;

webOSTV가 같은 네트워크 상에 있다면, TV를 등록하고 제어 해볼 수 있습니다.&#x20;

1. TV를 구분할 alias 를 입력해줍니다
2. TV의 IP정보를 입력해줍니다
3.  "추가하기"버튼을 눌러줍니다.

    <figure><img src="../../.gitbook/assets/image (2) (3).png" alt=""><figcaption><p>기기 추가 정보 입력</p></figcaption></figure>
4. 잠시 기다리면 TV 카드가 추가된 것을 확인할 수 있습니다.\
   ![](<../../.gitbook/assets/image (12) (3).png>)

### 서브기기 제어하기

연동된 서브기기들을 제어 해볼 수 있습니다. 서브기기 카드를 누르면 제어 할 수 있는 화면이 나옵니다. 제어 패널 안에서는 각 기기의 상세한 상태 값 또한 확인할 수 있습니다. 상태 값 및 제어 목록은 기기의 capability 파일을를 바탕으로 생성됩니다.

나만의 기기 타입을 만들면 허브를 통해 내가 만든 기기를 등록하고 제어  수 있습니다. \
새로 타입을 정의하는 방법은 [Custom Sub Device 가이드](../../fundamentals/damda-device/custom-sub-device/)를 참고하시기 바랍니다.

#### TV 제어하기

1. TV 카드를 누릅니다.&#x20;
2.  기기 제어 패널에서 setVolume에 원하는 값을 입력합니다.&#x20;

    <figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>기기 제어 카드 (webOSTV setVolume 예제)</p></figcaption></figure>
3. "실행하기"를 클릭합니다.&#x20;
4. TV의 볼륨이 2로 설정됩니다.&#x20;
