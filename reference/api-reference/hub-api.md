# Hub API

업데이트 예정입니다

{% swagger method="post" path="" baseUrl="/devices" summary="서브 기기 등록" %}
{% swagger-description %}
디바이스 타입 별 profile을 참고하여 요청합니다.

\


등록 가능한 device_type 리스트는 GET /deviceTypes 로 확인할 수 있습니다.
{% endswagger-description %}

{% swagger-parameter in="body" name="alias" required="true" type="String" %}
사용자가 식별 하기 위한 기기의 별칭
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" required="true" type="String" %}
등록하려는 기기의 디바이스 타입

등록가능한 디바이스 타입 리스트 중 선택 (GET /deviceTypes)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="preferences" required="true" type="Dictionary" %}
기기 등록 시 필요한 정보 기기타입의 profile을 확인하여 작성
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="delete" path="" baseUrl="/devices/{device_id}" summary="서브 기기 삭제" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}
