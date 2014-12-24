---
layout: post
title: 초보자를 위한 Jekyll Blog 시작하기
date: 2014-12-24 17:45:08
tags: jekyll blogging easyjekyll
---

[GitHub Pages를 이용해서 지킬 블로그 만들기](http://halryang.net/Start-Blogging-With-Jekyll/) 글을 올리고 지금까지 조금의 시간이 흘렀다. 처음 지킬 블로그를 시작하면서 적은 글이었기에 지금 보는 한량넷과는 차이가 있다.

일단 가장 큰 차이점은 이전 글에서는 터미널에서 로컬에 Jekyll을 설치하고 나서 GitHub에 사이트를 푸쉬해서 시작했다면, 지금 이글을 올리는 [한량넷](http://halryang.net)은 이미 기본적인 설정이 되어 있는 테마인 [Jekyll Now](https://github.com/barryclark/jekyll-now)의 GitHub Repository(줄여서 레포, Repo)를 Fork해서 커스터마이징한 결과라는 점이다. 나처럼 코딩에 대한 지식이 없는 사람이 Jekyll 블로그를 시작하려고 한다면 후자의 방법을 선택하는 것이 훨씬 낫다.

Jekyll Now는 정말 빠르게 블로그를 시작할 수 있도록 도와주지만 내가 사용하기엔 약간 아쉬운 기능들이 있었다. 그래서 그것을 보완한 과정과 보완한 버전을 EasyJekyll이라는 이름([easyjekyll repo](https://github.com/easyjekyll/easyjekyll.github.io/), [Demo](https://github.com/easyjekyll/easyjekyll.github.io/))으로 따로 만들어 봤다. Jekyll Now를 Fork해서 적용하는 것과 과정은 똑같으니 아래의 과정은 한번 읽어 보는 것이 좋다.

## Jekyll Now로 시작하기
Jekyll Now([데모](http://www.jekyllnow.com/))는 GitHub에 Jekyll 블로그를 더 쉽게 설치할 수 있도록 도와주는 테마다. 지킬 블로그를 수 분 안에 만들 수 있다고 나와있는데, 금방 만들 수 있는 것은 분명하다.  

[SmashingMagazine의 글](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/)을 읽고 차근차근 따라하면 Jekyll Now를 설치하고 포스팅을 하는 데까지 성공할 것이다. 과정을 간단히 정리하자면 아래와 같다.

1. Jekyll Now([GitHub Repo](https://github.com/barryclark/jekyll-now#quick-start)) Fork 하기
	1. 먼저 [GitHub](http://github.com)에 가입이 되어 있어야 한다.
	2. Fork 하는 방법은 [SmashingMagazine의 글](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/) 중간에 gif 파일로 잘 설명되어 있다.
2. Fork한 repo의 이름을 `사용자이름.github.io`로 변경한다.
	1. 일단 여기선 Master에 설정하는 것을 전제로 한다.
3. 이제 커스터마이징을 시작한다.
	1. `_config.yml`이라는 파일이 전반적인 설정을 관리하는 파일이다.
		* 사이트(블로그)의 이름과 설명(description)을 설정한다.
4. 블로그에 첫 글을 작성한다.
	1. 샘플로 들어 있는 `/_posts/2014-3-3-Hello-World.md`를 열고 내용을 블로그에 올리기 원하는 내용으로 수정한다.
	2. 파일의 이름을 `년-월-일-제목.md`의 형태로 작성 날짜에 맞추어 바꾼다.
	3. Front matter라고 부르는 파일의 시작 부분에 layout(보통 블로그 포스트는 그냥 post라고 적으면 된다), title(글의 제목)을 필요에 따라 바꾼다.
5. 이제 http://사용자이름.github.io 로 접속하면 자신의 지킬 블로그를 볼 수 있다.

GitHub Repo에 있는 파일을 수정, 삭제하거나 새로운 파일을 올릴 때는 3가지의 방법이 있다.

* GitHub.com에서 직접 수정
* [Prose](http://prose.io/) 써드파티 에디터를 사용
* Repo를 로컬에 복제(Clone)해서 로컬에서 수정한 다음에 GitHub Repo에 Push
	* 나는 로컬에서 내가 좋아하는 에디터를 사용하는 것이 좋아서 이 방법을 사용하고 있다. 놀부님의 [완전초보를 위한 깃허브](http://j.mp/18GPAt2)와 [Atlassian에서 제공하는 튜토리얼](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config)을 읽어보면 도움이 된다.

여기까지가 Jekyll + GitHub Pages + Jekyll Now(theme)을 설정하는 방법이다. 이대로 만족스럽다면, 더 설정할 필요 없이 블로그를 운영해도 된다. 나는 필요한 기능을 몇 가지 추가해서 쓰고 있다.

## 페이지를 나눠서 보여주기
Jekyll Now의 처음 세팅에서 가장 큰 아쉬움은 페이지 나누기(pagination) 설정이 안 되어 있는 것이었다. 이렇게 되면 처음 블로그에 글이 얼마 없을 때는 몰라도 글이 쌓이면서 첫 페이지에 엄청난 글의 목록이 쌓일 것이다. 이것을 방지하기 위해 한 페이지에 나올 글의 개수를 정하고, 나머지는 다음 페이지에 쌓이도록 설정한다. `_config.yml`에 paginate 옵션을 추가하고 `index.html`에 paginated posts와 pagination link를 위한 코드를 삽입한다.

## 전체글(Archive)을 한 곳에 모으기
[Archives in Jekyll - mitsake](http://www.mitsake.net/2012/04/archives-in-jekyll/)의 글에서 월 단위로 모으는 방법을 알게 되어 날짜 표현 방식만 약간 수정해서 적용했다. `archive.md` 파일을 만들어서 지킬 루트 폴더에 두고 `/_layouts/default.html` 파일에 링크를 추가하여 적용할 수 있다.

## 태그 시스템 적용하기
[놀부님의 글](http://nolboo.github.io/blog/2014/01/09/upgrade-jekyll-github-blog/#태그와_카테고리)과 GitHub Repo를 참고해서 태그 시스템을 적용했다.

> 1. `search.json`과 `post.json`을 만들어 각 포스트의 태그를 포함하는 일종의 데이터베이스 역할을 하는 파일을 만든다.
> 2. 각 태그 검색의 결과 페이지인 search.html을 만든다.
> 3. 필요한 자바스크립트를 적용한다. (`_layouts/default.html`, `_layouts/post.html` 수정하고 css 적용)

이렇게 설정하고 나면 블로그 글의 front matter에 `tags: jekyll blogging tagging` 의 형식으로 태그를 입력해서 사용할 수 있다.

## 태그 클라우드 페이지 만들기
태그를 알파벳 순으로 나열하는 `tags.md`파일을 만들어 지킬의 루트 폴더에 두고 `_layouts/default.html`에서 불러 온다. CSS도 약간 손을 봐야 보기 좋은 모양의 태그 클라우드가 나온다. 나는 [서울비 블로그](http://seoulrain.net)의 [GitHub repo](https://github.com/seoulrain/seoulrain.github.io)를 참고하여 만들었다.

## 반응형 동영상 임베딩(Responsive Video embedding)
Jekyll Now는 반응형 디자인으로 화면이 작은 모바일 환경에서 봐도 블로그를 보기에 문제가 없다. 그러나 동영상을 삽입한 경우 임베딩한 동영상은 충분히 반응형이 아니어서 작은 화면에서 YouTube 동영상이 잘려서 나온다. 그래서 `js/fluidvids.js`파일을 넣고 불러와서 사용한다. `<iframe>` 태그를 이용해서 영상을 삽입하면 알아서 반응형으로 보여준다.

## 참고하기 좋은 글

* [지킬로 깃허브에 무료 블로그 만들기 - @n0lb00's Blog](http://nolboo.github.io/blog/2013/10/15/free-blog-with-github-jekyll/ "지킬로 깃허브에 무료 블로그 만들기 - @n0lb00's Blog")
* [지킬 한글 번역 사이트](http://jekyllrb-ko.github.io/ "Jekyll • 심플하고 블로그 지향적인 정적 사이트")