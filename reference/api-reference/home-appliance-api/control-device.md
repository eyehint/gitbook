# 가전 제어

사용자의 가전을 제어하는 방법을 설명합니다.

### 사용할 API

* GET /devices
* GET /devices/profile/{device-id}
* POST /devices/{device-id}

### Sequence

1. 먼저 [가전 목록 조회 API](apis/get-devices.md)(GET/devices)를 이용하여, LG ThinQ 플랫폼에 등록된 사용자의 가전 목록을 가져와야 합니다. 이 과정은 처음 한 번만 수행하면 되고, 목록을 한 번 가져온 후에는 매번 수행할 필요는 없습니다.
2. 가전 목록에서 제어 대상 디바이스의 device-id 값을 확인하고, 이 값을 이용하여 [가전 프로파일 조회 API](apis/get-devices-profile-device-id.md)(GET /devices/profile/{device-id})를 호출합니다.
3. 호출 응답으로 받은 가전 프로파일을 바탕으로 해당 디바이스에 대한 제어 명령을 생성합니다. 제어 명령은 가전 프로파일에서 제어를 원하는 속성을 찾아 name과 value를 쌍으로 표현합니다.
4. device-id와 제어 명령을 이용하여 [가전 제어 API](control-device.md)(POST /devices/{device-id})를 호출합니다.
5. API 응답으로 가전 제어 결과를 반환받습니다.

<figure><img src="https://developer.damda.lge.com/assets/img/thinq2.png" alt=""><figcaption></figcaption></figure>
