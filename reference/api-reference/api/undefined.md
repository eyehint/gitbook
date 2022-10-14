# 가전 상태 조회

사용자의 가전 상태를 조회하는 방법을 설명합니다.

### 사용할 API

* GET /devices
* GET /devices/{device-id}

### Sequence

1. 먼저 [가전 목록 조회 API](apis/undefined.md)(GET /devices)를 이용하여, LG ThinQ 플랫폼에 등록된 사용자의 가전 목록을 가져와야 합니다. 이 과정은 처음 한 번만 수행하면 되고, 목록을 한 번 가져온 후에는 매번 수행할 필요는 없습니다.
2. 가전 목록에서 상태를 조회할 디바이스의 device-id 값을 확인하고, 이 값을 이용하여 [가전 상태 조회 API](apis/undefined-1.md)(GET /devices/{device-id})를 호출합니다.

<figure><img src="https://developer.damda.lge.com/assets/img/thinq1.png" alt=""><figcaption></figcaption></figure>

