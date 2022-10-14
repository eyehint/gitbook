# Step4. 디버깅 하기

## 1. Debugging 용 Test Component 코드 작성

아래의 예제코드를 작성합니다.

Log를 Debugging 콘솔에서 보기위해서는\
&#x20;   1\.  json type으로 작성되어야 합니다\
&#x20;   2\. json 안에는 level, message, function, timestamp의 요소가 들어가야 합니다.\
&#x20;   3\. Log의 path는 /var/log/damda/{file이름} 이어야 합니다.

<pre><code># main.py
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

## 2. Test Component 생성 및 배포

component를 배포하기 위해서 DAMDA Console에서 생성합니다.

<figure><img src="../.gitbook/assets/image (16) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

아래와 같이 생성된 component의 배포를 진행합니다.

<figure><img src="../.gitbook/assets/image (10) (1) (1).png" alt=""><figcaption></figcaption></figure>

## 3.Debugging Console

아래와 같이 콘솔들을 확인 할 수 있습니다.

{% content-ref url="../fundamentals/damda-tools/debugging-console.md" %}
[debugging-console.md](../fundamentals/damda-tools/debugging-console.md)
{% endcontent-ref %}
