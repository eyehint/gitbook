# Table of contents

* [DAMDA Overview](README.md)
* [Quick Start](quick-start/README.md)
  * [개발환경 구성하기](quick-start/setup-env.md)
  * [Hello DAMDA 따라하기](quick-start/hello-damda.md)
  * [ThinQ 연결하기](quick-start/connect-with-thinq.md)
  * [내 컴포넌트 로그 확인하기](quick-start/check-component-log.md)
  * [내 컴포넌트 원격 제어하기](quick-start/remote-control-component.md)

## FUNDAMENTALS

* [DAMDA 기기](fundamentals/damda-device/README.md)
  * [DAMDA Installer](fundamentals/damda-device/damda-installer/README.md)
    * [DAMDA Installer 설치하기](fundamentals/damda-device/damda-installer/setup-damda-installer.md)
    * [DAMDA 설치하기](fundamentals/damda-device/damda-installer/install-damda.md)
    * [DAMDA 삭제하기](fundamentals/damda-device/damda-installer/uninstall-damda.md)
    * [DAMDA Installer 삭제하기](fundamentals/damda-device/damda-installer/remove-damda-installer.md)
  * [DAMDA Debugging Console](fundamentals/damda-device/debugging-console.md)
  * [DAMDA Home](fundamentals/damda-device/damda-home/README.md)
    * [기기 등록 하기](fundamentals/damda-device/damda-home/register-device.md)
    * [기기 등록 해제하기](fundamentals/damda-device/damda-home/unregister-device.md)
  * [Custom Sub Device](fundamentals/damda-device/custom-sub-device/README.md)
    * [Capability](fundamentals/damda-device/custom-sub-device/capability.md)
    * [Profile](fundamentals/damda-device/custom-sub-device/profile.md)
    * [Functions](fundamentals/damda-device/custom-sub-device/functions.md)
* [DAMDA Cloud](fundamentals/damda-cloud/README.md)
  * [계정 관리](fundamentals/damda-cloud/manage-account/README.md)
    * [계정 생성하기](fundamentals/damda-cloud/manage-account/undefined.md)
    * [기타](fundamentals/damda-cloud/manage-account/undefined-1.md)
  * [컴포넌트 관리](fundamentals/damda-cloud/manage-component/README.md)
    * [DAMDA Components](fundamentals/damda-cloud/manage-component/damda-components.md)
    * [컴포넌트 초기화하기](fundamentals/damda-cloud/manage-component/initialize-component.md)
    * [컴포넌트 개발하기](fundamentals/damda-cloud/manage-component/develop-component-code.md)
    * [컴포넌트 생성하기](fundamentals/damda-cloud/manage-component/create-component.md)
    * [컴포넌트 배포하기](fundamentals/damda-cloud/manage-component/deploy-component.md)
* [DAMDA Tools](fundamentals/damda-tools/README.md)
  * [DAMDA CLI](fundamentals/damda-tools/damda-cli/README.md)
    * [Configuration](fundamentals/damda-tools/damda-cli/configuration.md)
    * [Component](fundamentals/damda-tools/damda-cli/component.md)
    * [Device](fundamentals/damda-tools/damda-cli/device.md)
    * [Deployment](fundamentals/damda-tools/damda-cli/deployment.md)
  * [DAMDA Simulator](fundamentals/damda-tools/damda-simulator.md)

## REFERENCE

* [API Reference](reference/api-reference/README.md)
  * [ThinQ API](reference/api-reference/thinq-api.md)
    * [APIs](reference/api-reference/thinq-api/apis/README.md)
      * [ThinQ 계정 등록](reference/api-reference/thinq-api/apis/post-account.md)
      * [사용자 홈 목록 가져오기](reference/api-reference/thinq-api/apis/get-home.md)
      * [사용자 기기 목록 가져오기](reference/api-reference/thinq-api/apis/get-home-devices.md)
      * [기기 등록하기](reference/api-reference/thinq-api/apis/post-device.md)
      * [기기 정보 가져오기](reference/api-reference/thinq-api/apis/get-device.md)
      * [기기 제어하기](reference/api-reference/thinq-api/apis/post-device-control.md)
      * [기기 삭제하기](reference/api-reference/thinq-api/apis/delete-device.md)
      * [기기 정보 전달하기](reference/api-reference/thinq-api/apis/post-monitoring.md)
    * [Error / Exceptions](reference/api-reference/thinq-api/error-exceptions.md)
  * [Hub API](reference/api-reference/hub-api.md)
    * [APIs](reference/api-reference/hub-api/apis/README.md)
      * [지원 기기타입 가져오기](reference/api-reference/hub-api/apis/get-device-types.md)
      * [기기 profile 가져오기](reference/api-reference/hub-api/apis/get-profiles-device-type.md)
      * [Capability 가져오기](reference/api-reference/hub-api/apis/get-capabilities-id-version.md)
      * [서브 디바이스 등록하기](reference/api-reference/hub-api/apis/post-devices.md)
      * [서브 디바이스 삭제하기](reference/api-reference/hub-api/apis/delete-devices-device-id.md)
      * [등록 / 삭제 결과 확인하기](reference/api-reference/hub-api/apis/get-progress-register-register-id.md)
      * [서브 디바이스 리스트 조회](reference/api-reference/hub-api/apis/get-devices.md)
      * [서브 디바이스 정보 조회](reference/api-reference/hub-api/apis/get-devices-device-id.md)
      * [서브 디바이스 상태 조회](reference/api-reference/hub-api/apis/get-devices-device-id-state.md)
      * [서브 디바이스 제어](reference/api-reference/hub-api/apis/post-devices-device-id-control.md)
      * [제어 결과 확인](reference/api-reference/hub-api/apis/get-devices-device-id-control.md)
      * [서브 디바이스 상태 모니터링](reference/api-reference/hub-api/apis/undefined.md)
      * [전체 서브 디바이스 상태 모니터링](reference/api-reference/hub-api/apis/undefined-1.md)
    * [Types](reference/api-reference/hub-api/types/README.md)
      * [Device](reference/api-reference/hub-api/types/device.md)
      * [DeviceState](reference/api-reference/hub-api/types/devicestate.md)
  * [가전 API](reference/api-reference/home-appliance-api/README.md)
    * [가전 상태 조회](reference/api-reference/home-appliance-api/check-status.md)
    * [가전 제어](reference/api-reference/home-appliance-api/control-device.md)
    * [APIs](reference/api-reference/home-appliance-api/apis/README.md)
      * [공통 | Headers](reference/api-reference/home-appliance-api/apis/common-headers.md)
      * [공통 | Response](reference/api-reference/home-appliance-api/apis/common-response.md)
      * [공통 | Error](reference/api-reference/home-appliance-api/apis/common-error.md)
      * [가전 목록 조회](reference/api-reference/home-appliance-api/apis/get-devices.md)
      * [가전 상태 조회](reference/api-reference/home-appliance-api/apis/get-devices-device-id.md)
      * [가전 Profile 조회](reference/api-reference/home-appliance-api/apis/get-devices-profile-device-id.md)
      * [가전 제어](reference/api-reference/home-appliance-api/apis/post-devices-device-id.md)
      * [EMP Access Token 발급](reference/api-reference/home-appliance-api/apis/emp-access-token.md)
      * [Event/Push Callback (Websocket)](reference/api-reference/home-appliance-api/apis/event-push-callback-websocket.md)
    * [Types](reference/api-reference/home-appliance-api/types/README.md)
      * [Device Type](reference/api-reference/home-appliance-api/types/device-type.md)
      * [Device Profile](reference/api-reference/home-appliance-api/types/device-profile.md)
  * [webOS TV API](reference/api-reference/webos-tv-api/README.md)
    * [TV 리스트 조회](reference/api-reference/webos-tv-api/get-webostv.md)
    * [TV 등록](reference/api-reference/webos-tv-api/post-webostv.md)
    * [Custom SSAP Command](reference/api-reference/webos-tv-api/custom-ssap-command.md)
    * [Control](reference/api-reference/webos-tv-api/control/README.md)
      * [ON/OFF](reference/api-reference/webos-tv-api/control/on-off.md)
      * [Channel](reference/api-reference/webos-tv-api/control/channel.md)
      * [Audio](reference/api-reference/webos-tv-api/control/audio.md)
      * [App](reference/api-reference/webos-tv-api/control/app.md)
      * [UI 및 기타](reference/api-reference/webos-tv-api/control/ui-and-others.md)
    * [Remote](reference/api-reference/webos-tv-api/remote.md)
    * [Subscribe](reference/api-reference/webos-tv-api/subscribe.md)
* [Samples](reference/samples.md)
  * [Hello DAMDA](reference/samples/hello-damda.md)
  * [ThinQ 연결하기](reference/samples/control-app.md)
  * [Debugging App](reference/samples/debugging-app.md)
  * [가전 App](reference/samples/home-appliance-app.md)
  * [Proto Sub Device](reference/samples/proto-sub-device.md)
  * [TV화면 캡쳐 + AWS Rekognition](reference/samples/tv-capture-with-rekognition.md)
  * [DAMDA Hub](reference/samples/damda-hub.md)
