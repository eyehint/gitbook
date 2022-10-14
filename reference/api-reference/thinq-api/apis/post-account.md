---
description: DAMDA 기기 내부에 사용자의 계정을 등록 또는 변경 할 수 있습니다.
---

# POST /account

## 담다ers를 참고하시기 바랍니다.&#x20;

#### Body&#x20;



{% swagger method="post" path="/account" baseUrl="http://{device_ip}:8951" summary="사용자의 ThinQ 계정 정보를 DAMDA 기기에 저장한다. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="message-id" type="String" %}
로깅 목적, 미 입력 자동 생성 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" %}
EMP ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
EMP Password
{% endswagger-parameter %}
{% endswagger %}
