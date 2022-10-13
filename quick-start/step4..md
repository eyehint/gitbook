# Step4. 디버깅 하기

## 1. Debugging 용 Test Component 코드 작성

아래의 예제코드를 작성한다.

로그는 json type이며 key 값에는 level, message, function, timestamp가 들어가야한다.

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

component를 배포하기 위해서 DAMDA Console에서 생성한다

![](<../.gitbook/assets/image (16).png>)

![](<../.gitbook/assets/image (8).png>)

배포를 진행한다.

![](<../.gitbook/assets/image (10).png>)

