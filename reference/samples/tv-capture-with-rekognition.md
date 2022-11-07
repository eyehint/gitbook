# TV화면 캡쳐 + AWS Rekognition

{% file src="../../.gitbook/assets/celebrity.zip" %}

## Dependency

[webOS TV](../api-reference/webos-tv-api/) component를 사용하는 예제입니다.

## 예제

AWS Rekognition의 [Recognizing celebrity](https://docs.aws.amazon.com/rekognition/latest/dg/celebrities.html)를 활용한 예제입니다.

1. 샘플 코드(celebrity.zip) 다운받으세요
2. image/celebrities\_recognizer.py #11 에서 본인의 [AWS credential](https://docs.aws.amazon.com/rekognition/latest/dg/setting-up.html)을 사용해주세요.

<figure><img src="../../.gitbook/assets/image (45) (1).png" alt=""><figcaption></figcaption></figure>

* 컴포넌트 script (privilege 모드)
  1. 초기설정 스크립트 : (python3 -m venv /damda/venv/celebrity) && (/damda/venv/celebrity/bin/pip install -r {root}/celebrity/requirements.txt)
  2. 실행 스크립트 : /damda/venv/celebrity/bin/python {root}/celebrity/app.py

## 예제 실행 화면

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>
