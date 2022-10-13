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
   ![](<../../../.gitbook/assets/image (7) (2).png>)   ![Menu > "damda" 검색](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2Fo39jplzTATPRX20mYEYA%2Fimage.png?alt=media\&token=df171290-7f44-4663-8051-69634d1bca2d)\

2. Installer에 DAMDA id와 password 입력합니다\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FfrLwzBJnl9AwXT8JUcwk%2Fimage.png?alt=media\&token=1c2059d0-6a04-479a-b65f-bb9427f9e038)\

3. "Uninstall" 버튼 클릭합니다\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2F864kgxVwYclEkleIzerW%2Fimage.png?alt=media\&token=033a5c0f-44ac-4158-8ed8-16e7b5c366df)\

4. 제거 과정이 진행됩니다. 완료 된 후 OK 버튼을 눌러 종료 시킬 수 있습니다.\
   ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FRh4AIubxze8T8vvwIMp1%2Fimage.png?alt=media\&token=e3e99647-d337-4e95-8cd2-10bc59892a60) ![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fl3Km0lGSEvAZ1z7FtNCb%2Fuploads%2FNnHNHTEJ8GzFiiF0apnz%2Fimage.png?alt=media\&token=35c5dbbb-0141-413d-9592-57108e1ed659)
{% endtab %}

{% tab title="CLI" %}
damda uninstall 명령을 sudo 로 실행합니다

```shell
sudo damda uninstall
```
{% endtab %}
{% endtabs %}
