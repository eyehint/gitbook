# Capability

Capability는 기기가 가지고 있는 상태 정보(attributes) 및 제어 명령(commands)에 대해 정의한 파일입니다.

## Template

```json
{
    "id": [capability의 id (type=string)],
    "version": [capability 버전 (type=int)],
    "name": [기기의 이름 (type=string)],
    "attributes": {
        [attribute 이름 1 (type=string)]: {
            "schema": {
                "properties": {
                    "value": {
                        "type": [value의 type. "string", "integer", "boolean"가능 (type=string)],
                        { value의 범위를 정의. 자세한 정의는 예시 참고 (type=dictionary)}
                    }
                }
            }
        },
        [attribute 이름 2 (type=string)]: {
            ...
        },
        ...
    },
    "commands": {
        [command 이름 1 (type=string)]: {
            "name": [function의 method 이름 (type=string)],
            "arguments": [function의 argument 리스트 (type=dictionary list)]
        },
        [command 이름 2 (type=string)]: {
            "name": [function의 method 이름 (type=string)],
            "arguments": [
                {
                    "name": [argument name (type=dictionary list)],
                    "schema": {
                        "type": [argument의 type. "string", "integer", "boolean" 가능 (type=string)],
                        "minimum": [argument의 minimum값을 제한할 경우 작성. 필요없으면 생략 가능 (type=int)],
                        "maximum": [argument의 maximum값을 제한할 경우 작성. 필요없으면 생략 가능 (type=int)]
                    }
                }
            ]
        },
        ...
    }
}
```

* 생략 가능이라고 적혀있지 않은 요소는 모두 필수로 들어가야합니다.
* **attribute의 이름과 command이름은 반드시 camelCase로 정의**합니다.
* attribute의 경우 각 타입별로 value의 범위를 정의한 예시는 다음과 같습니다. 특별히 value값 범위 지정이 필요하지 않다면 생략합니다.

{% tabs %}
{% tab title="string 타입" %}
value에 들어와야하는 string 값이 정해져 있지 않은경우, type만 작성합니다.

```json
"value": {
    "type": "string",
}
```



value에 들어와야하는 값이 명확히 정해져있는 경우, enum 사용합니다.

```json
"value": {
    "type": "string",
    "enum": [
        "on",
        "off"
    ]
}o
```
{% endtab %}

{% tab title="integer 타입" %}

{% endtab %}

{% tab title="bool 타입" %}

{% endtab %}
{% endtabs %}

*
  * string 타입\

  * int
  * bool \
    true / false 중에 입력되므로 별도로 정의하지 않고, 생략 합니다\
    \

* arguments의 경우
  1.  빈값이면 \[]로 value를 주면됩니다.

      | `"arguments":[]` |
      | ---------------- |
  2. 값을 작성하는 경우, control 명령에 의해 호출 될 때, parameter가 범위안에 들어와있는지 체크합니다
  3. 현재 minimum / maximum 체크만을 지원합니다
