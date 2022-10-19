# Functions

hub와 기기를 연동하기위하여 필요한 코드를 정의합니다. python 으로 작성해야 합니다.

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

기기에서 추가로 필요한 모듈이 있다면, functions 밑에 디렉토리를 만들어 함께 포함시킵니다. 예를 들어 기기를 실제로 제어하기위해서 필요한 모듈 같은 것들이 포함될 수 있습니다. 추가한 모듈, 라이브러리의 디렉토리 명은 자유롭게 정의 가능합니다. 모듈을 import 할 때, 상대 경로로 작성합니다.

### 등록/삭제/제어/상태 함수 작성

등록 / 삭제 함수는 반드시 하나씩 만들어주어야 합니다.

제어 함수는 기기가 할 수 있는 제어 명령 별로 하나씩 존재합니다.

상태 함수가 없을 경우 기기 상태 정보가 바뀌는 것을 알 수 없습니다.

모든 함수는 device\_info를 첫번째 인자로 받습니다. device\_info에 포함된 정보는 다음과 같습니다.

#### device\_info

json 형태로 정의되어 있습니다.

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

* hub에서 서브 기기를 등록할  호출되는 함수입니다&#x20;
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

* hub에서 서브 기기를 삭제할 때 호출되는 함수입니다
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

* hub에서 서브 기기를 제어할 때 호출되는 함수입니다
* @control 데코레이터 사용합니다
* 서브기기가 수행할 수 있는 각 제어 명령 별로 하나의 함수를 작성합니다. 함수 이름은 capability에 정의된 command의 name과 연결됩니다
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

* hub에서 서브기기의 상태값을 모니터링 하기위해 호출하는 함수입니다
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
    &#x20;`{profile의 components id}{capability의 id}{attribute name}` \
    이때 capability의 id와 attribute name의 첫글자는 대문자로 작성
  * 기기로 부터 받은 상태값을 넘겨줍니다

{% code title="set_attribute 호출 방법" %}
```python
set_attribute([기기의 id], [attribute key값], [상태값])
```
{% endcode %}

## Functions Example

<details>

<summary>webOSTV.py</summary>

```python
# webOSTV와 연동되는 코드
# TV와 통신을 위해 PyWebOSTV 모듈을 import해서 사용하고 있습니다
from devices import get_register, get_unregister, get_control, get_state, set_attribute
from .pywebostv import PyWebOSTV


register = get_register()
unregister = get_unregister()
control = get_control()
state = get_state()


@register
def register_tv(device_info):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()


@unregister
def unregister_tv(device_info):
    pass


@control
def power_on(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.power_on()


@control
def power_off(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.power_off()


@control
def set_volume(device_info, component: str, capability: str, volume: int):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.set_volume(volume)
    return {
        "volume": volume
    }


@control
def volume_up(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.volume_up()
    return {}


@control
def volume_down(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.volume_down()
    return {}


@control
def mute(device_info, component: str, capability: str, mute: bool):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.mute(mute)
    return {}


@control
def channel_up(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.channel_up()
    return {}


@control
def channel_down(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.channel_down()
    return {}


@control
def home(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.home()
    return {}


@control
def back(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.back()
    return {}


@control
def ok(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.ok()
    return {}


@control
def left(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.left()
    return {}


@control
def right(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.right()
    return {}


@control
def up(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.up()
    return {}


@control
def down(device_info, component: str, capability: str):
    ip = device_info["preferences"]["ip"]
    tv_remote_controller = PyWebOSTV(ip).get_tv_remote_controller()
    tv_remote_controller.down()
    return {}

@control
def capture(device_info, component: str, capability: str, upload_uri: str):
    ip = device_info["preferences"]["ip"]
    tv_controller = PyWebOSTV(ip).get_tv_controller()
    tv_controller.register_tv()
    tv_controller.capture(upload_uri)
    return {}

@state(exceptions=(Exception, ), countdown=10)
def subscribe_volume(device_info):
    ip = device_info["preferences"]["ip"]
    device_id = device_info["deviceId"]
    try:
        tv_controller = PyWebOSTV(ip).get_tv_controller()
        tv_controller.register_tv()

        def volume_callback(response):
            try:
                try:
                    volume = response["payload"]["volumeStatus"]["volume"]
                    muted = response["payload"]["volumeStatus"]["muteStatus"]
                except KeyError:
                    volume = response["payload"]["volume"]
                    muted = response["payload"]["muted"]
                set_attribute(device_id, "online", True)
                set_attribute(device_id, "mainWebOSTVVolume", volume)
                set_attribute(device_id, "mainWebOSTVMuted", muted)
            except:
                pass

        tv_controller.subscribe_volume(volume_callback)
    except Exception as e:
        set_attribute(device_id, "online", False)
        raise e


@state(exceptions=(Exception, ), countdown=10)
def subscribe_channel(device_info):
    ip = device_info["preferences"]["ip"]
    device_id = device_info["deviceId"]
    try:
        tv_controller = PyWebOSTV(ip).get_tv_controller()
        tv_controller.register_tv()

        def program_info_callback(response):
            try:
                program_name = response["payload"]["programName"]
                channel_name = response["payload"]["channelName"]
                channel_number = response["payload"]["channelNumber"]
                set_attribute(device_id, "online", True)
                set_attribute(device_id, "mainWebOSTVProgramName", program_name)
                set_attribute(device_id, "mainWebOSTVChannelName", channel_name)
                set_attribute(device_id, "mainWebOSTVChannelNumber", channel_number)
            except:
                pass

        tv_controller.subscribe_program_info(program_info_callback)
    except Exception as e:
        set_attribute(device_id, "online", False)
        raise e

```

</details>

<details>

<summary>sensorLight.py</summary>

```python
# 시뮬레이터 Light와 연동되는 코드
# 시뮬레이터와 통신을 위해 SimulatorAdapter 모듈을 import해서 사용하고 있습니다
from devices import get_register, get_unregister, get_control, get_state, set_attribute
from .sensorSimulator.sensorAdapter import SimulatorAdapter

register = get_register()
unregister = get_unregister()
control = get_control()
state = get_state()


@register
def register_light(device_info):
    device_info = SimulatorAdapter(device_info).start_register()
    return device_info


@state(exceptions=(Exception,), countdown=10)
def get_light_state(device_info):
    print(f"init: light sensor state {device_info}")

    def handle_sensor_data(device_id: str, status: dict):
        print(f"received: light sensor state :: {status}")
        turn_on = status["turnOn"]
        brightness = status["brightness"]
        set_attribute(device_id, 'mainSensorLightTurnOn', turn_on)
        set_attribute(device_id, 'mainSensorLightBrightness', brightness)
    SimulatorAdapter(device_info).start_monitoring(handle_sensor_data)


@unregister
def unregister_light(device_info):
    device_info = SimulatorAdapter(device_info).unregister()
    return device_info


@control
def up_brightness(device_info, component: str, capability: str):
    SimulatorAdapter(device_info).control(
        {"command": "up", "param": {"target": "brightness"}})


@control
def down_brightness(device_info, component: str, capability: str):
    SimulatorAdapter(device_info).control(
        {"command": "down", "param": {"target": "brightness"}})


@control
def set_brightness(device_info, component: str, capability: str, value: int):
    SimulatorAdapter(device_info).control(
        {"command": "set", "param": {"target": "brightness", "value": value}})


@control
def on(device_info, component: str, capability: str):
    SimulatorAdapter(device_info).control(
        {"command": "on", "param": {}})


@control
def off(device_info, component: str, capability: str):
    SimulatorAdapter(device_info).control(
        {"command": "off", "param": {}})


@control
def toggle(device_info, component: str, capability: str):
    SimulatorAdapter(device_info).control(
        {"command": "toggle", "param": {}})
p
```

</details>
