---
layout: post
title: Scrivener로 지킬 블로깅하기
date: 2016-02-26 11:04:31
tags: Scrivener jekyll blogging python
---
저는 Scrivener를 구입만 해두고 제대로 쓰고 있지 않았습니다. 긴 글을 작성하는데 가장 특화된 앱이라는 핑계를 대면서 그냥 익숙하고 단순하게 사용할 수 있는 Byword를 주로 쓰고 있었습니다. Scrivener를 사용하려고 하니 요새 글을 쓰는 곳이 그나마 가끔 지킬 블로그에 글을 올리는 게 전부라서 지킬 블로그에 글을 올리는 초안을 작성하는 정도로 사용할까 하고 시작했습니다.

### 컴포지션 모드 - 글을 쓰는 환경 만들기

![](/images/ss_20160225_164759.jpg)

일단 [한량넷](halryang.net)으로 글을 올리기 위한 프로젝트를 하나 만들었습니다. 그리고 나서 가장 중요한 컴포지션 모드를 손보기 시작합니다. Scrivener에는 전체화면 모드가 두 가지입니다. 바인더, 에디터, 인덱스로 구분되는 메인 윈도우 화면을 전체화면 크기에 맞게 확장시켜 주는 통상적인 전체화면 모드와 , 글을 쓰는 데에만 집중할 수 있는 화면을 만들어 주는 컴포지션 모드입니다. 컴포지션 모드는 사용자가 선택한 배경에, 종이가 한 장 주어진 느낌입니다. 기본적으로 Typewriter 모드 − 글을 쓰는 부분이 항상 화면의 가운데에 위치하도록 하는 모드 − 가 적용되어 있습니다.

### 마크다운으로 글 내보내기

저는 Byword, Focused, Desk.PM 등의 마크다운 기반 에디터를 주로 사용하는데, Scrivener는 마크다운을 기반으로 하는 앱은 아닙니다. 그래도 .md 파일을 내보내는 것에는 전혀 문제가 없습니다. 저는 메뉴바에서 `File - Sync - with External Folder...` 를 사용해서 Scrivener에서 쓴 글 중 Draft 폴더에 해당하는 글만 외부 폴더와 동기화했습니다. 동기화하는 외부 폴더는 Dropbox 안에 있는 폴더로 지정해서 어디서나 접근이 가능합니다. 동기화 설정을 이리저리 만져봤지만, 모든 글을 다 외부 폴더와 동기화 하면 Research, Clipping, 심지어 폴더 트리로 쓰고 있는 각각의 폴더까지도 .md 파일로 생성되어 동기화하는 외부 폴더가 많이 복잡해졌습니다. 그래서 바인더에 기본으로 있는 Draft 아래에 넣어 두고 실제로 작업하고 있는 글만 외부에서도 접근할 수 있도록 해뒀습니다.

![](/images/ss_20160225_172145.png)

위의 스크린샷에서 위의 푸른 형광 사각형 안에 외부폴더 경로를 지정하고, 빨간 사각형 안에서 플레인텍스트 .md 파일로 저장하도록 설정했습니다. 맨 아래에 있는 Automatically convert plain text paragraph spacing 을 체크하면 외부에서 파일을 수정하고 동기화하는 경우 단락 구분이 없어지고 그냥 줄바꿈만 한 것으로 나오니, 같은 모습을 유지하려면 저 부분을 체크하지 마세요. 각자 환경에 맞도록 설정하시면 됩니다.

### 외부에서 글에 접근, 수정하기

저는 아이폰이나 아이패드에서 Editorial, Drafts 으로 주로 글을 쓰는데, 둘 다 Dropbox에서 노트를 가져와 수정할 수 있습니다. 게다가 특정 노트에 Append 하는 액션도 있습니다. 이제 Scrivener를 쓰기 시작하는 단계이니 아직은 만들지 않았지만, 앞으로 필요하면 Draft 폴더에 따로 Idea나 resource 같은 글을 만들어서 맥을 쓸 수 없을 때에도 아이폰이나 아이패드에서 블로깅 아이디어나 나중에 참고할만한 자료들을 Append하는 방식으로 모아 놓을 수도 있겠지요.

아직 나오지는 않았지만, [Scrivener for iOS를 개발중이라는 소식](http://www.literatureandlatte.com/blog/?p=658)도 있습니다. 알파 테스트를 진행하고 있다니 아무래도 자체 앱이 나오면 그것이 동기화 등 안정성에서 훨씬 좋을 것으로 기대합니다.

### 지킬 블로그에 포스팅하기

Scrivener에서 바인더 내에 `Published` 폴더를 만들고 그 아래 글을 넣으면 저절로 깃헙에 커밋, 푸시까지 된다면 가장 좋겠지만, Scrivener는 블로깅 툴이 아닙니다.[^1] 그래서 가장 나은 방법을 찾아야 합니다. 제가 선택한 방법은 일단 글이 다 완성이 되면 외부 폴더와 동기화해서 완성된 글을 외부 폴더로 내보냅니다. 이후 파이썬 스크립트를 실행합니다. 저는 왕초보이기에 아주 엉망인 스크립트이지만 아래 공유해봅니다.

```
#-*- coding: utf-8 -*-
import sys
reload(sys)
sys.setdefaultencoding('utf-8')

import subprocess

from sys import argv
from datetime import datetime
from os.path import exists
import os
import re

script, from_file = argv

# from_file 의 내용을 indata 변수로 지정합니다.
in_file = open(from_file)
indata = in_file.read()

# From_file의 파일명을 지킬 포스트 파일명 형식에 맞도록 바꿔줍니다.
p = re.compile('\s-\d+-[.]md')
sp = re.compile('\s')

m = p.search(from_file)
if m:
	from_file = p.sub('.md', from_file)
	from_file = sp.sub('-', from_file)
	print('renaming file name to', from_file)
else:
	from_file = sp.sub('-', from_file)
	print('renaming file name to', from_file)

# dt는 스크립트를 실행하는 날짜와 시각입니다.
dt = datetime.now()

# to_file은 argv로 받은 원본 파일명 앞에 지킬 포스트 폴더와 날짜를 넣어봅니다.
to_file_date = dt.strftime("%Y-%m-%d-")
to_file = '/로컬/지킬의/_posts/폴더/' + to_file_date + from_file

# 지킬 포스트 폴더에 보내려는 파일명과 동일한 파일이 있는지 확인합니다.
print "Does the output file exist? %r" % exists(to_file)
print "Ready, hit RETURN to continue, CTRL-C to abort."
raw_input()

# post_date는 지킬 포스트의 YAML 머리말에 들어가는 date 형식에 맞추었습니다.
post_date = dt.strftime("%Y-%m-%d" + ' ' + "%H:%M:%S")

# post_title, post_tags 변수값을 raw_input으로 받습니다.
post_title = raw_input("Title: ")
post_tags = raw_input("Tags: ")

# 이제 YAML 머리말을 indata 앞에 넣어 outdata를 만듭니다.

outdata = """---
layout: post
title: %s
date: %s
tags: %s
---
%s
""" % (post_title, post_date, post_tags, indata)

out_file = open(to_file, 'w')
out_file.write(outdata)

print "%s is copied to %s" % (from_file, to_file)

out_file.close()
in_file.close()

# GitHub에 add & commit & push

os.chdir('/로컬/지킬의/루트/폴더')

subprocess.call(["git", "add", "."])
subprocess.call(["git", "commit", "-m", "Post published"])
subprocess.call(["git", "push", "-u", "origin", "master"])
```

이 파이썬 스크립트는 완성된 파일을 선택한 후 파일명을 지킬 블로그 포스트 파일명에 맞도록 바꾸고, YAML에 들어갈 제목과 태그를 입력해서 로컬 지킬의 `_posts` 폴더로 복사합니다. 마지막으로 깃헙에 커밋, 푸시까지 합니다. 이 스크립트는 로컬에 지킬이 있고, 깃헙과 연결이 되어 있다는 전제로 만들었습니다.

[^1]: 게다가 제가 지금까지 찾아 본 바로는 전술한 기능을 지원하는 블로깅 앱도 없습니다.
