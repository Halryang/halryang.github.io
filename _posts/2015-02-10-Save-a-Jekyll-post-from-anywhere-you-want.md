---
layout: post
date: 2015-02-10 10:38:23
title: 편집기를 가리지 않고 지킬 포스트를 작성하는 Keyboard Maestro Macro
tags: Keyboard-Maestro automation jekyll blogging productivity
---

이전 글[^1]에서도 시도했던 바인데, 제가 쓰는 앱에서는 편하게 사용할 수 있는 매크로였지만, 모든 편집기에서 사용할 수 있는 것이 아니었습니다. 이번 매크로([매크로 다운로드](http://dl.dropboxusercontent.com/u/18183807/Jekyll_Save_post.kmmacros))는 정말로 어떤 편집기를 써도 가능하게 하는 것이 목표입니다. 어느 앱에서나 글을 마크다운 형식으로 작성하고 매크로를 실행하면 됩니다.

![](/images/ss_Jekyll_Save_post_KMM.png)

### 매크로 설명
컨셉은 어디서든 글을 다 작성한 이후에 매크로를 실행하면 글의 제목과 태그를 입력하는 팝업창이 뜨고 제목과 태그를 입력하면 저절로 글의 최상단에 YAML 머리말을 넣습니다. 그리고 YAML 머리말을 포함한 텍스트 전부를 지킬 포스트 폴더에 새로운 파일명으로 저장하는 것입니다. 글 제목, 태그, 글 전체 텍스트, 포스트 파일명을 각각 변수로 지정했습니다.

### 사용법
마지막에 파일을 어디에 저장할지 정하는 곳만 각자의 필요에 따라 바꿔서 사용하시면 됩니다. 저는 지킬 블로그에 카테고리는 사용하지 않습니다. 태그 외에 카테고리도 지정해야 하는 경우엔 Post Title, Post Tags 변수를 YAML 머리말에 넣는 것을 참고하셔서 카테고리 변수를 하나 더 추가하면 됩니다.

[^1]: [어느 앱에서나 지킬 블로그에 포스팅을 간단하게 하자](http://halryang.net/post-to-jekyll-from-anywhere/)
