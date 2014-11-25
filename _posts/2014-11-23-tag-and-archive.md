---
layout: post
title: 지킬에 태그시스템과 아카이브 페이지 추가
date: 2014-11-23 14:08:06
tags: jekyll blogging
---
## 태그 추가
지킬에서 블로그를 운영하기로 하고 태그와 아카이브 페이지를 만든다는 것이 좀 늘어졌습니다. 관련 정보는 찾아 놓아서 적용하기만 하면 되겠다고 생각했지만 [지킬 공식 문서](http://jekyllrb-ko.github.io/docs/plugins/)에 포함된 플러그인으로 태그를 만드는 데는 모두 실패했습니다. 프로그래밍을 전혀 모르는 제가 그냥 보고 따라하기엔 어려웠습니다. 놀부님의 [포스팅](http://nolboo.github.io/blog/2014/01/09/upgrade-jekyll-github-blog/)을 보고 따라해보고 놀부님의 깃허브 레포까지 포크해서 봤습니다만 소개해주신 방법으로 하는 것은 실패했습니다. 거의 모든 방법들이 자바스크립트를 사용하는 것으로 보였고, 저는 js 파일을 어디에 놓고 어떻게 적용하는지를 몰라서 힘들었습니다.

다시 처음부터 시작하는 마음으로 검색에 돌입, 드디어 시키는대로 따라하니 작동하는 태그 시스템을 찾았습니다. 제가 참고한 글은 [Tags in Jekyll](http://charliepark.org/tags-in-jekyll/ "Tags In Jekyll")입니다. 이 글의 설명대로 tag_index.html 파일과 tag_gen.rb 파일을 만들어서 각각 `"_layouts"`, `"_plugins"` 폴더에 넣으니 로컬에서 빌드한 지킬 사이트에 "tag" 폴더가 생기고 그 안에 각 태그 별로 하위폴더가 생성되었습니다. 생성된 태그 목록이 보이는 스타일이 마음에 들지 않아서 태그 목록 스타일링은 놀부님의 깃허브를 포크한 데서 많이 가져다가 썼습니다.

지금은 글 제목 아래에 태그들이 나열되고 태그를 누르면 눌린 태그를 포함하는 글의 목록이 나옵니다. 블로그 전체에 있는 태그들의 목록이 나오는 페이지는 그렇게까지 필요할까 싶어서 아직 만들지 않았습니다. 나중에 필요하다고 생각하면 다시 또 열심히 검색해야지요.

## 전체글 목록도 추가
전체 글 목록은 훨씬 간단하게 추가했습니다. [Joshua Lande의 글](http://joshualande.com/jekyll-github-pages-poole/ "How I Created a Beautiful and Minimal Blog Using Jekyll, Github Pages, and poole · Joshua Lande")을 참고해서 지킬의 루트 디렉토리에 archive.md 를 만들고 default layout에 페이지 링크를 추가했습니다. 글이 작성된 날짜가 나오는 방식만 간단히 바꿨습니다.

여기서 월별로 아카이빙하는 더 깔끔한 방법을 [seoulrain](!@t)님의 [블로그](http://seoulrain.net)를 통해 알게 되어 얼른 따왔습니다. 지금 보시는 [전체 글](http://halryang.github.io/archive/)이 결과물입니다.