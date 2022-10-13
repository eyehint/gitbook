# Step4. 디버깅 하기

## 1. Debugging 용 Test Component 만들기

<pre><code><strong># main.py
</strong><strong>import logging
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

위와 같이 logging을 할 수 있는 코드를 만든다.

로그는 json type이며 key 값에는 level, message, function, timestamp가 들어가야한다.

