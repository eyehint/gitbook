---
description: DAMDA 제품에 배포한 내 컴포넌트를 원격으로 제어하기 위한 방법을 설명합니다.
---

# 내 컴포넌트 원격 제어하기

## 1. 기본 구조

DAMDA 기기 내부는 다음과 같은 구조로 구되어 있습니다 .

<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

* ThinQ Agent : ThinQ Server와 담다 기기간의 Communication을 담당합니다.&#x20;
* MQTT Broker : ThinQ Agent와 사용자 컴포넌트간의 제어 명령을 전달합니다.&#x20;
  * 'damda/control' : ThinQ Server로 부터 해당 기기로 전달되는 제어 명령이 저장됩니다.&#x20;
  * 'damda/control/result' : 컴포넌트로 전달된 제어 명령에 대한 결과를 저장합니다.



## 2. 사용자 컴포넌트에서 제어명령 받기

#### 0. 준비

기본적으로 TPA에서 (또는 다른 담다 기기에서) 전달되는 제어 명령은 사용자가 직접 정의하여 사용합니다.&#x20;

_\[제어 명령 예시 - 담다 허브 : 서브기기 조회하기 ]_

```
{
   "ctrlKey":"Hub",
   "command":"getSubDeviceList"
   "dataSetList":{}
}
```

#### 1. 제어 메시 받기

ThinQ Agent 는 서버로 부터 전달받은 제어 명령을 기기 내부의 MQTT Broker에 그대로 publish 합니다.\
이때 사용되는 MQTT Broker의 정보는 다음과 같습니다.

{% hint style="success" %}
MQTT Broker Information

* host : localhost
* port : 1883
* topic : damda/control
{% endhint %}

사용자 컴포넌트는 내부 MQTT의 Topic을 Subscribe하여 제어 명령을 획득할 수 있습니다.&#x20;

#### 2. 제어 결과 회신하기

ThinQ Server는 제어 명령을 전달한 뒤 특정시간 동안 결과를 대기합니다. \
(만약 결과가 회신되지 않는 경우 Timeout Exception이 발생합니다)

따라서 원할한 컴포넌트 제어를 진행하기 위해서는 반드시 제어 결과를 회신하여야 합니다.&#x20;

제어 메시지 받기와 마찬가지로 사용자 컴포넌트와 ThinQ Agent는 MQTT 기반 통신을 진행합니다. \
즉, 사용자 컴포넌트가 기기 내부의 MQTT Broker (Topic : damda/control/result)로 결과를 publish하면, \
ThinQ Agent는 그 값을 subscribe하여 ThinQ Server로 전달합니다.&#x20;

{% hint style="warning" %}
ㅡdfd
{% endhint %}
