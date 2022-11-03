# TV 리스트 조회

{% swagger method="get" path="" baseUrl="/webostv" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "192.168.0.41": "%5bLG%5d%20webOS%20TV%20OLED55GXKNA"
}
```
{% endswagger-response %}
{% endswagger %}

## GET /webostv

### Description

같은 네트워크에 연결된 webOS TV를 SSDP 프로토콜을 통해 조회합니다.

### Request

n/a

### Response

```
{
    "192.168.0.41": "%5bLG%5d%20webOS%20TV%20OLED55GXKNA"
}
```

