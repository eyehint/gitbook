# Functions

기기의 실제 동작을 정의합니다. python 으로 작성해야 합니다.

/opt/damda/sub-devices/user-devices/functions 하위에 위치합니다

## 코드 작성 가이드 <a href="#id-webostv" id="id-webostv"></a>

### 파일명&#x20;

디바이스 타입명과 동일하게 파일명을 작성합니다. `{deviceType}.py`

모든 기기 코드는 아래와 같은 코드로 시작합니다.

```python
from devices import get_register, get_unregister, get_control, get_state, update_state
 
register = get_register()
unregister = get_unregister()
control = get_control()
state = get_state()
```

### 코드에서 사용하는 커스텀 라이브러리 추가

기기에서 추가로 필요한 모듈이 있다면, functions 밑에 디렉토리를 만들어 함께 포함시킵니다. 디렉토리 명은 자유롭게 사용가능합니다. import 할 때, 상대 경로로 작성합니다.

### 등록/삭제/제어/상태 함수 작성

등록 / 삭제 함수는 반드시 하나씩 만들어주어야 합니다

모든 함수는 device\_info를 첫번째 인자로 받습니다. device\_info에 포함된 정보는 다음과 같습니다.

| key          | description                     |
| ------------ | ------------------------------- |
| deviceId     | 등록된 기기 ID                       |
| deviceType   | 등록된 기기의 타입                      |
| deviceState  | 기기의 최근 상태 정보                    |
| alias        | 기기를 식별할 수 있는 이름                 |
| registeredAt | 기기가 등록된 시간                      |
| preferences  | 기기와 연결하기 위해 필요한 정보              |
| profile      | 기기의 profile (상세 정의는 Profile 참고) |

#### 등록 함수 작성

* 기기 등록 시 호출되는 함수입니다&#x20;
* @register 데코레이터 사용합니다&#x20;
* 함수명은 자유롭게 정의 가능합니다
* 파리미터로 device\_info 받습니다

```python
@register
def [함수명](device_info):
  # 기기 등록 코드 작성
  # 등록에 필요한 parameter는 "device_info["preferences"]['preference_name' 에 정의한 값]"으로 받아옴py
```

#### 삭제 함수 작성

* 기기 삭제 시 호출되는 함수입니다
* @unregister 데코레이터 사용합니다
* 함수명은 자유롭게 정의 가능합니다
* device\_info를 파라미터로 받습니다

```
@unregister
def [함수명](device_info):
  # 기기 등록 해제 코드 작성
  # 특별히 기기에 해제요청을 보내지 않아도 되면 pass로 비워두어도 됨
```

#### 제어 함수 작성

* 기기를 제어 시 호출되는 함수입니다
* @control 데코레이터 사용합니다
* 함수 이름은 capability에 정의된 command의 name과 연결됩니다
* 제어 명령은 device\_info 이외에 기본 인자로 component 정보와 capability 정보를 추가로 받습니다
* API의 응답 값으로 전달해줄 결과를 return 합니다. 없는 경우는 생략합니다
* 제어명령에 추가 arguments 가 필요한 경우 2가지 작업이 필요합니다. sync가 안맞으면 정상적으로 실행되지 않습니다
  * capability에 명시합니다
  * python 코드에 method parameter 마지막에 추가합니다

```
@control
def [command_name](device_info, component: str, capability: str [, 추가 parameter가 있다면 작성]):
  # 기기 제어 코드 작성
```

#### 상태 함수 작성

* 기기의 상태값을 모니터링 하기 위한 함수입니다
* @state 데코레이터 사용하고, exception과 countdown을 함께 작성해주어야 합니다
* 함수명은 자유롭게 정의 가능합니다.
* 파리미터로 device\_info 받습니다

```python
@state(exceptions=(Exception, ), countdown=10)
def [함수명](device_info):
  # 기기의 상태값을 지속적으로 받아오는 함수 코드 작성
  # 상태값 변화를 감지하면 set_attribute를 호출하여 업데이트된 상태값을 알려주어야함
```

* 상태값 변화를 감지하면, set\_attribute를 호출하여 hub에 상태값이 변했음을 알려줍니다
* set\_attribute를 호출하지 않으면 상태값 변화가 저장되지 않습니다
* set\_attribute 호출 방법
  * 기기 id 는 device\_info로 부터 받아옵니다. \
    `device_info["device_id"]`
  * 규칙에 맞춰 attribute의 key값을 만들어줍니다.\
    &#x20;`[profile의 component id][capability의 id][attribute name]` \
    이때 capability의 id와 attribute name의 첫글자는 대문자로 작성
  * 기기로 부터 받은 상태값을 넘겨줍니다

{% code title="set_attribute 호출 방법" %}
```python
set_attribute([기기의 id], [attribute key값], [상태값])
```
{% endcode %}
