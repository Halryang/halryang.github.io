---
layout: post
title: 지킬 포스팅의 자동화
date: 2014-11-23 22:22:32
tags: jekyll automation Keyboard-Maestro TextExpander
---
워드프레스에서 지킬로 갈아타면서 워드프레스보다 편하게 글을 내보내는 방법이 부족한 상태입니다. 워드프레스를 쓸때도 그랬지만 플러그인을 최소로 사용해서 가능한 가벼운 상태로 지킬을 유지하려고 생각중입니다.

## YAML 머리말
지킬에서 블로그에 올릴 포스트에는 YAML 머리말이 필요합니다. 저는 지금 지킬에서 태그까지 사용하기 때문에 YAML 머리말에 layout, title, date, tags를 입력해야 합니다. 이 과정은 [TextExpander][9855-0001]를 이용하는 중입니다. 미리 지정한 약어(abbreviation)를 입력하면 title과 tags에 내용을 입력할 수 있는 팝업창이 나오고 내용을 입력하면 date와 layout은 저절로 채워집니다. 저는 iOS에서 글을 작성할 경우를 생각해서 TextExpander를 이용해서 snippet을 만들었지만 충분히 [Keyboard Maestro][9855-0002]로도 구현할 수 있습니다.

## 지킬 포스트 파일명 생성 매크로
저는 주로 [nvALT][9855-0003]와 [Byword][9855-0004]를 사용해서 마크다운 문서를 작성합니다. 글로벌 매크로를 만들어서 nvALT나 Byword 두 앱중 어디서나 하나의 매크로로 지킬 파일명을 지정하고 지킬 로컬 사이트의 `_posts` 폴더에 리턴키만 누르면 저장할 수 있도록 하는 매크로입니다. 매크로는 [이곳](/assets/Jekyll-file-name-maker.kmmacros)에서 받을 수 있습니다. 매크로 작동 과정은 다음과 같습니다.

### 이 매크로의 장점
* 포스트 작성 시간과 공백에 신경쓸 필요 없이 원하는 파일명만 생각하고 지정하면 됩니다.

### 지킬 포스트 파일 형식의 변수 설정
1. 파일 이름으로 쓸 텍스트 입력창 띄우기
2. 입력된 텍스트 앞에 `년-월-일-` 삽입하기
3. 텍스트에 공백(whitespace)이 있는 경우 `-`으로 치환하기
4. 위까지의 결과를 "Jekyll_File_name"이라는 변수로 세팅

변수가 설정된 이후엔 세 가지 경우로 나뉘어 다음 과정이 진행됩니다.

### nvALT에서 작성하는 경우
1. "⌘+E"을 이용해서 파일 내보내기
2. 내보낼 파일명을 `Jekyll_File_name 변수.md`으로 설정
3. 내보낼 목적 폴더를 지킬 로컬 사이트의 `_posts` 폴더로 지정

### Byword에서 작성하는 경우
1. "⌘+S"을 이용해서 파일 저장하기
2. 내보낼 파일명을 `Jekyll_File_name 변수.md`으로 설정
3. 내보낼 목적 폴더를 지킬 로컬 사이트의 `_posts` 폴더로 지정

### nvALT나 Byword 외의 곳에서 매크로가 실행된 경우
* Jekyll_File_name 변수를 시스템 클립보드에 저장

## 지킬 터미널 명령어 스니펫
TextExpander를 이용해서 자주 입력하는 터미널 명령어를 간편하게 입력합니다. Keyboard Maestro를 사용해서 Time pause를 주면 일련의 명령어들을 저절로 입력되게 할 수 있겠지만 그렇게까지 하는 것보다 터미널에서 각 명령어에 따른 결과를 보면서 입력하는 것이 낫다고 생각합니다.

* jswqq → jekyll serve -w
* jbqq → jekyll build
* git acqq → git add . -A && git commit -m "(이곳에 커서 위치)"
* git pushqq → git push -u origin master

[9855-0001]: http://smilesoftware.com/TextExpander/
[9855-0002]: http://www.keyboardmaestro.com/
[9855-0003]: http://brettterpstra.com/projects/nvalt/
[9855-0004]: http://bywordapp.com/