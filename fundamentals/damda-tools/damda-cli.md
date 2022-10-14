---
description: 웹브라우저에서 DAMDA Console을 통한 개발 대신에 CLI(Commend Line Interface) 통해서도 개발할 수 있습니다.
---

# DAMDA CLI

## DAMDA CLI 설치하기

// 설치파일은 추후 제공될 예정입니다.

<pre class="language-shell"><code class="lang-shell"><strong>$ git clone ssh://git@mod.lge.com:2222/tip/damda-cli-typer.git
</strong>$ cd damda-cli-typer
(requirements.txt 파이썬 환경 설정)
$ python setup.py install
 
 
$ damda --install-completion    # [Optional] Install completion for the current shell</code></pre>

## 사용법

### Configuration

Commands to manage DAMDA account information so that you can use functions such as component creation/deletion/deployment by accessing the DAMDA cloud with the DAMDA CLI

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### Component

Commands to create/delete/list components

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

### Device

Commands to retrieve device information and a list of components installed in the device

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

### Deployment

Commands to check component deployment and deployment results

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>
