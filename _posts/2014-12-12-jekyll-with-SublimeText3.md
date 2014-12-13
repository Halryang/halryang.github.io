---
layout: post
title: Sublime Text 3로 지킬 포스트 작성하기
date: 2014-12-12 11:07:43
tags: SublimeText3 app
---
<div id="toc"><p class="toc_title"></p></div>
## Sublime Text 3 소개
[Sublime Text](http://www.sublimetext.com/)는 워낙 유명한 텍스트에디터다. 주로 코딩에 쓰는 앱으로 보이고 첫인상이 뭔가 코딩을 위해 태어난 사람이 사용하게 생겼지만 나같은 일반 사용자에게도 충분히 매력적인 앱이다. 부드러운 사용자 인터페이스와 뛰어난 활용성을 가진 Sublime Text 3를 이용해서 지킬에 올릴 글을 작성하는 데 어떻게 활용할 수 있을지 소개한다. 지금 Sublime Text 3는 베타버전이다. 그러나 얼마든지 실사용이 가능한 정도이며 [여기서](http://www.sublimetext.com/3 "Sublime Text - Download") 내려받을 수 있다. 베타버전이라고 딱히 기능의 제한은 없고 구매를 유도하는 팝업창이 가끔 나온다.

## Sublime Text 3의 특징

### 막강한 개인화(Customize Anything)
테마, 색조합, 키 바인딩, 메뉴, 축약어(snippets), 매크로, 완성 등 많은 것을 사용자에 맞도록 개인화가 가능하다. 평소 작은 부분에서도 내게 딱 맞게 설정해서 사용하기 좋아하는 나는 이 개인화 기능이 정말 마음에 든다. 파일 유형이나 프로젝트에 따라 세팅을 각각 다르게 설정할 수도 있다.

### 크로스 플랫폼 지원
위에 적은 개인화를 완벽히 설정해서 사용하다 보면 Sublime Text 3가 아닌 다른 환경에서 글을 작성하는 것이 볼편할 수 있다. Sublime Text 3는 OS X, Windows와 linux를 지원한다. 모바일 환경이 아닌 곳에선 충분히 같은 사용자 경험을 가지고 동일한 세팅으로 글을 작성할 수 있다.

### 집중 모드(Distraction Free mode)
집중해서 글을 작성해야 할 때, 요새 나오는 훌륭한 앱들에서 제공하는 Distraction free mode를 써 본 사람들은 어느 앱에서나 집중할 수 있는 모드를 지원하는지 찾을 것이다. Sublime Text 3도 집중할 수 있는 모드를 지원한다. 전체 화면에 글만 작성할 수 있도록 해주어 다른 것에 집중력을 뺏기지 않고 글을 쓰는 행위에만 집중할 수 있다.

### 다양한 마크업에 따른 문법 강조
나는 거의 모든 글을 마크다운을 사용해서 작성한다. 정말 짧은 인터넷에서 본 글을 스크랩 할 때도 이젠 마크다운의 인라인 링크 형식으로 적어 두니까 아마 마크다운에서 헤어나오려면 상당히 힘들 것 같다. Sublime Text 3에는 **Package Control**(OS X 단축키: `⌘+⇧+P`)이라는 막강한 기능이 있는데 이것을 이용하면 기본적으로 제공되는 문법 강조 외에도 다양한 강조 설정이 가능하다.

## Sublime-Jekyll - 지킬 포스팅을 편하게 해주는 패키지

이름에서부터 알 수 있듯 Sublime Text 3에서 지킬을 편하게 쓸 수 있게 해주는 패키지다. 이 패키지를 이용하면 지킬 사이트의 포스트와 초안(draft)에 더 편하게 접근할 수 있다. 현재 2.1 버전이 최신이다.

### 설치
Package Control(OS X 단축키: `⌘+⇧+P`)를 사용해서 `Package Control: Install Package` 커맨드를 선택, **Jekyll**을 검색해서 엔터키를 누르면 설치가 시작된다. 설치 후 재시작해야 패키지를 사용할 수 있다.

### 설치 후 세팅
`readme.md`에 모두 들어 있는 내용이지만 간단히 훑어본다. 이 패키지를 설치한 후에는 `Sublime Text → Preferences → Package Settings → Jekyll → Settings - User`에 들어가서 `"posts_path"`와 `"drafts_path"`의 경로를 각자의 지킬 사이트의 `"_posts"`와 `"_drafts"`폴더에 맞도록 설정해야 한다. 맥은 Unix 스타일(*e.g. /Users/사용자이름/site/_posts*)로 경로를 설정해야 제대로 작동한다. 그 밖에 `"default_post_syntax"`와 `"default_post_layout"`등을 필요에 따라 설정한다.

### Sublime-Jekyll에 들어 있는 내용
![nsoa_console.png](https://github.com/23maverick23/sublime-jekyll/raw/master/Screenshots/sublime_jekyll_screenshot.png "sublime-jekyll")

#### 문법 강조

- HTML(Jekyll)
- JSON(Jekyll)
- Markdown(Jekyll): 지킬을 위한 마크다운 문법 강조이므로 당연히 YAML 머리말도 보기 좋게 보여준다.
- Textile(Jekyll)

#### 커맨드와 키바인딩

- Jekyll: New post => `CMD+K, CMD+P`
- Jekyll: New draft => `CMD+K, CMD+F`
- Jekyll: Insert current date => `CMD+K, CMD+D`
- Jekyll: Insert current datetime => `CMD+K, CMD+T`
- Jekyll: Open post...
- Jekyll: Open draft...
- Jekyll: Promote draft to post...

기본 키바인딩을 덮어쓰게 된다. 덮어쓰는 것이 싫은 경우 `Preferences > Package Settings > Jekyll > Key Bindings – User`에서 원하는 단축키를 설정할 수 있다.

#### 축약어(snippets)

축약어를 쓰는 방법은 원하는 축약어를 적은 후 탭키(`⇥`)를 누르면 된다. assign, capture, case, comment, va, cycle, eslif, for, front-matter, gist, highlight, if, ifelse, include, post_url, raw, unless, when의 축약어가 있다.

## 맺으며
이제야 Sublime Text 3를 사용하기 시작했다. 하지만 확실히 편한 부분이 있다고 생각되어 이렇게 글을 남겨본다. 더 편하게 사용할 수 있는 팁을 공유하면 좋겠다는 바람도 섞여 있다. 앞으로도 더 편한 글쓰기 & 블로깅 환경을 찾아야지. 물론 내가 귀찮아서 조금이라도 편한 방법을 찾아가는 거다. ;)