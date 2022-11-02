---
description: DAMDA 제품에 배포한 내 컴포넌트를 디버깅하기 위한 방법을 설명합니다.
---

# 내 컴포넌트 로그 확인하기

## 1. Debugging 용 Test Component 코드 작성

내 코드의 로그를 [Debugging Console](../fundamentals/damda-tools/debugging-console.md)에서 보기 위해서는,\
&#x20;   1\.  로그가 json type으로 작성되어야 합니다\
&#x20;   2\. json 안에는 level, message, function, timestamp의 요소가 들어가야 합니다.\
&#x20;   3\. Log File의 path는 `/var/log/damda/`아래에 저장합니다. 파일명은 자유롭게 사용할 수 있습니다.

로그를 남기고 확인해보는 예제코드를 만들어 보겠습니다. 아래와 같은 예제 코드를 작성합니다. 파일명은 main.py로 작성합니다.

<pre class="language-python"><code class="lang-python"># main.py
<strong>import logging
</strong>import json
import time

logger = logging.getLogger()

formatter = logging.Formatter(json.dumps({
    "level":"%(levelname)s",
    "message":"%(message)s",
    "function":"%(funcName)s",
    "timestamp":"%(asctime)s",
}))
file_handler = logging.FileHandler('/var/log/damda/com.damda.public.hello_debug.log')
file_handler.setFormatter(formatter)
logger.addHandler(file_handler)
logger.setLevel("INFO")

if __name__ == '__main__':
    while True:
        logger.info("Hello debug world")
        time.sleep(30)</code></pre>

작성한 컴포넌트를 hello\_debug.zip으로 압축합니다

{% hint style="info" %}
hello\_debug.zip의 구조는 다음과 같습니다.&#x20;

hello\_debug.zip\
ㄴ main.py
{% endhint %}

## 2. Test Component 생성 및 배포

component를 배포하기 위해서 DAMDA Console에서 생성합니다.

component명은 자유롭게 사용할 수 있으나 다른 사용자의 컴포넌트와 중복이 되면 안됩니다.

자세한 컴포넌트 생성 가이드는 [컴포넌트 생성](../fundamentals/damda-cloud/undefined-1/undefined.md) 페이지를 참고하세요

<figure><img src="../.gitbook/assets/image (16) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (8) (4).png" alt=""><figcaption></figcaption></figure>

아래와 같이 생성된 component의 배포를 진행합니다.

<figure><img src="../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

## 3.Debugging Console

`DAMDA Console -> 디바이스 탭 -> 배포한 디바이스 ID 오른쪽에 detail 클릭 -> 디버깅 콘솔 버튼을 클릭`하여 디버깅 콘솔에 접속할 수 있습니다.

<figure><img src="../.gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>

디버깅 콘솔 관련된 상세한 내용은 아래 페이지에서 확인해주세요

{% content-ref url="../fundamentals/damda-tools/debugging-console.md" %}
[debugging-console.md](../fundamentals/damda-tools/debugging-console.md)
{% endcontent-ref %}
