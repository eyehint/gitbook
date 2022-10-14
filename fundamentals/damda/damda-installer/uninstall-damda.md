---
description: >-
  DAMDA를 삭제하는 가이드 입니다. DAMDA를 제거하면 라즈베리파이에 설치된 DAMDA 기기가 삭제됩니다. DAMDA Console의
  "디바이스"탭에서도 기기가 사라지게 됩니다.
---

# DAMDA 삭제하기

{% tabs %}
{% tab title="GUI" %}
1. DAMDA Installer 아이콘을 눌러서 실행합니다\
   \[RaspberryPi OS]                                         \[Ubuntu mate]\
   ![](<../../../.gitbook/assets/image (23).png>)   ![Menu > "damda" 검색](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2Fo39jplzTATPRX20mYEYA%2Fimage.png?alt=media\&token=df171290-7f44-4663-8051-69634d1bca2d)\

2. Installer에 DAMDA id와 password 입력합니다\
   ![](<../../../.gitbook/assets/image (1).png>)\

3. "Uninstall" 버튼 클릭합니다\
   ![](<../../../.gitbook/assets/image (17).png>)\

4. 제거 과정이 진행됩니다. 완료 된 후 OK 버튼을 눌러 종료 시킬 수 있습니다.\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FRh4AIubxze8T8vvwIMp1%2Fimage.png?alt=media\&token=e3e99647-d337-4e95-8cd2-10bc59892a60) ![](<../../../.gitbook/assets/image (33).png>)
5. 제거가이 완료된 것을 확인합니다. DAMDA Console의 디바이스 탭을 새로고침 하면 삭제된 기기의 id가 더이상 보이지 않습니다\
   ![](<../../../.gitbook/assets/image (31) (1).png>) ![](<../../../.gitbook/assets/image (19).png>)
{% endtab %}

{% tab title="CLI" %}
damda uninstall 명령을 sudo 로 실행합니다

```shell
sudo damda uninstall
```

\
damda 제거가 정상적으로 되었는지 아래 명령어로 확인할 수 있습니다.

```shell
$ sudo damda info
DAMDA is not installed. No Device information.
```
{% endtab %}
{% endtabs %}
