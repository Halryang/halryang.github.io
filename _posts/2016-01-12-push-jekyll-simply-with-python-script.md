---
layout: post
title: 지킬 블로그 푸시를 간단하게 하는 파이썬 스크립트
date: 2016-01-12 11:56:56
tags: jekyll python script automation blogging github
---
GitHub Pages를 이용해서 지킬 블로그를 운영하는 경우, 로컬 폴더를 깃헙에 푸쉬해서 쓰게 됩니다. 약간의 변화를 줄때마다 깃헙에 add, commit, push 명령어를 입력하는 것이 귀찮아서 파이썬 스크립트를 짜봤습니다.

### Python Script for git add & commit & push a Jekyll site simply

``` python
#-*- coding: utf-8 -*-
import sys
reload(sys)
sys.setdefaultencoding('utf-8')

import subprocess
import os

os.chdir('/path/to/your/local/jekyll/folder/')

subprocess.call(["git", "add", "."])
subprocess.call(["git", "commit", "-m", "Put your commit message here"])
subprocess.call(["git", "push", "-u", "origin", "master"])
```

위의 스크립트는 [여기](https://dl.dropboxusercontent.com/u/18183807/jekyllpush.zip)에서 내려받을 수 있습니다.

### 스크립트 실행하기

터미널에서 명령어 `python /path/to/python/script/jekyllpush.py`를 입력해서 스크립트를 실행할 수도 있지만, Automator로 서비스를 만들어서 단축키를 지정하거나, 원하는 때에 상단 메뉴바에서 서비스를 선택해서 위의 파이썬 스크립트를 실행할 수 있습니다. 

![](/images/ss_20160112_114854.jpg)
Automator를 켜고 새로운 서비스 만들기를 엽니다.

![](/images/ss_20160112_113023.jpg)
왼쪽 Actions 패널에서 Utilities 라이브러리의 Rus Shell Script 액션을 오른쪽 패널로 드래그한 후 위 스샷과 같이 `python /path/to/python/script/jekyllpush.py` 를 입력합니다. 이제 적당한 이름으로 저장한 후 사용하시면 됩니다.
