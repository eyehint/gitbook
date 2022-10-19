---
description: 웹브라우저에서 DAMDA Console을 통한 개발 대신에 CLI(Commend Line Interface) 통해서도 개발할 수 있습니다.
---

# DAMDA CLI

## DAMDA CLI 설치하기

<pre class="language-shell"><code class="lang-shell"><strong>$ git clone ssh://git@mod.lge.com:2222/tip/damda-cli-typer.git
</strong>$ cd damda-cli-typer
(requirements.txt 파이썬 환경 설정)
$ python setup.py install
 
 
$ damda --install-completion    # [Optional] Install completion for the current shell</code></pre>

설치파일은 추후 제공될 예정입니다.

## 사용법

### Configuration

Commands to manage DAMDA account information so that you can use functions such as component creation/deletion/deployment by accessing the DAMDA cloud with the DAMDA CLI

#### config

Commands to set up a DAMDA account.

Command

```
$ damda configure [OPTIONS]
# OPTIONS:
#   --profile TEXT: [default:default]
```

Usage

&#x20; Case 1) set up an DAMDA account with the default profile

```
$ damda configure
DAMDA ID [default]: <Enter DAMDA ID>
DAMDA P/W[default]: <Enter DAMDA P/W>
```

&#x20; Case 2) set up an DAMDA account with the default profile

```
$ damda configure --profile test
DAMDA ID [test]: <Enter DAMDA ID>
DAMDA P/W[test]: <Enter DAMDA P/W
```

#### get-configuration

Command to get DAMDA account information for a specific profile.

Command

<pre><code><strong>$ damda get-configuration [OPTIONS]
</strong># OPTIONS:
#    --profile TEXT: [default: default]</code></pre>

Usage

&#x20; Case 1) set up an DAMDA account with the default profile

```
$ damda get-configuration
{'id': '<DAMDA ID>', 'pw': '<DAMDA P/W>'}
```

&#x20; Case 2)set up an DAMDA account with the default profile

```
$ damda get-configuration --profile test
{'id': '<DAMDA ID>', 'pw': '<DAMDA P/W>'}
```
