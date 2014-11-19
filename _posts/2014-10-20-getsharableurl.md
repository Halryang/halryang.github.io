---
layout: post
title: Copy Dropbox public link url to Clipboard - Keyboard Maestro Macro
date: 2014-10-20 23:35:35.000000000 +09:00
categories:
- Like
- Productivity
tags:
- automation
- dropbox public link
- Keyboard geek
- Keyboard Maestro
- Keyboard Maestro Macro
- LaunchBar
- workflow
status: publish
type: post
published: true
meta:
  _mytory_markdown_etag: 67295n
  mytory_md_path: http://dl.dropboxusercontent.com/u/18183807/wp/Copy%20Dropbox%20public%20link%20url%20to%20Clipboard.txt
  _edit_last: '1'
  slide_template: default
  _wpas_done_all: '1'
  post_views_count: '0'
  _likes: '0'
author:
  login: brandnewjf
  email: charmjf@gmail.com
  display_name: brandnewjf
  first_name: ''
  last_name: ''
---
## Dropbox의 Public 폴더 안의 파일의 공유 링크를 쉽게 얻자

 나처럼 Mytory markdown plugin을 사용해서 워드프레스에 포스팅하는 경우(워드프레스 포스팅 자동화에 관한 [이전 글](http://sunjin.us/automation-for-wp-posting/ "Automation for wp posting | SUNJIN") 참조) Dropbox의 공개링크 url이 필요하다. 그래서 Copy Dropbox public link url to Clipboard 라는 긴 이름의 Keyboard Maestro Macro를 만들었다. 매크로 이름에서 바로 오늘 소개할 매크로의 기능을 알 수 있다. Dropbox의 Public 폴더 안에 있는 파일의 공개링크주소를 클립보드에 복사한다. 이번 매크로에는 Automator로 만든 간단한 Workflow가 들어가 있다. Keyboard Maestro 내에서 파일을 선택하는 창을 띄울 수 있는지 몰라서 다른 방법을 찾다 보니 Automator를 사용하게 되었다. Keyboard Maestro에는 Automator workflow를 실행하는 액션이 있어서 Automator로 만든 workflow도 잘 녹아든다.

### 이 매크로의 장점

* 어느 앱에서 무슨 일을 하던 중에라도 Public 폴더 내의 파일을 선택하여 공개링크를 얻을 수 있다.
* Dropbox의 Public 폴더 내의 파일이라면 어떤 파일이든 공개 링크를 얻을 수 있다.
* Public 폴더 내의 하위 폴더에 들어가 있어도 전혀 문제 없다.

### 필요사항

* LaunchBar
* Keyboard Maestro
* Mac

### [Copy Dropbox public link url to Clipboard][2]

![](http://dl.dropboxusercontent.com/u/18183807/wp/URLtoCl.jpg)

군더더기 없이 단순하다. 'CopyPublicLink'라는 Automator workflow를 실행한 다음 'Dropbox public path to url'이라는 Keyboard Maestro Macro를 실행하는 두 단계로 나뉘어 있다. 

#### [Copy Public Link][3]

![](http://dl.dropboxusercontent.com/u/18183807/wp/automatorPL.jpg)

Automator Workflow는 새로운 Finder 윈도우를 열어 파일을 선택하는 것으로 시작한다. 여기서는 편의를 위해 Finder 창이 열릴 때 Dropbox의 Public 폴더를 기본으로 열도록 설정했다. 그 후엔 LaunchBar를 거쳐 'Copy to Clipboard' 액션으로 해당 파일의 경로를 클립보드에 복사한다.

#### [Dropbox public path to url][4]

![](http://dl.dropboxusercontent.com/u/18183807/wp/kmmPtURL.jpg)

 Dropbox public path to url 매크로에서는 위에서 얻어낸 파일의 경로를 공개링크 url로 바꾸어 클립보드에 저장한다. 나의 경우 Dropbox의 Public 폴더 내의 파일 경로는 `/Users/JF/Dropbox/Public/[파일명].[확장자]`이다. 맥에서 기본적인 경로에 Dropbox를 설치한 사람이라면 나와 비슷한 경로를 가질 것이다. 여기서 `/Users/[사용자명]/Dropbox/Public/`을 `http://dl.dropboxusercontent.com/u/[Dropbox-사용자-코드]/`로 바꿔야 한다. 그리고 파일명에 공백이 들어간 경우 `%20`과 같이 인코딩을 해야 url로 사용할 수 있다.
 
 `Dropbox-사용자-코드`에 들어갈 코드는 Dropbox의 Public 폴더 내의 아무 파일이나 우클릭해서 '공개 링크 복사'를 하면 `http://dl.dropboxusercontent.com/u/123456/[파일명].[확장자]`와 같이 클립보드에 복사된다. 위의 예에서는 '123456'이 본인의 Dropbox code이다.

 이제 이 매크로를 액션 순서대로 설명하면 다음과 같다.

1. `/Users/[사용자명]/Dropbox/Public/`을 지운다.
2. 남은 `[Public-folder-안의-하위폴더]/[파일명].[확장자]`를 URL을 위해 퍼센트 인코딩한다.
3. 클립보드에 앞에 `http://dl.dropboxusercontent.com/u/[Dropbox-사용자-코드]/`를 추가하여 클립보드에 복사한다.
4. 확인을 위해 클립보드에 복사된 내용을 잠시 보여준다.
 
 마지막으로 클립보드에 복사되는 url 주소는 `http://dl.dropboxusercontent.com/u/[Dropbox-사용자-코드]/[Public-folder-안의-하위폴더]/[파일명].[확장자]`이다. 물론 Public 폴더 안에 또다른 하위 폴더에 들어가 있는 파일이 아니라면 `http://dl.dropboxusercontent.com/u/[Dropbox-사용자-코드]/[파일명].[확장자]`의 형태로 클립보드에 복사된다.
 

### 매크로 사용법

 스크립트를 알면 훨씬 간단하게 매크로를 작성할 수 있겠다 싶었는데, Keyboard Maestro Macro 공유하는 방법을 검색하다가 [Matt Gemmell의 블로그](http://mattgemmell.com/keyboard-maestro-macros/ "Keyboard Maestro macros - Matt Gemmell")에서 정말 간단한 [매크로][1]를 발견했습니다. 파인더에서 파일 선택해서 매크로 실행하면 선택한 파일을 Dropbox의 Public 폴더로 이동하고, 공개링크주소는 클립보드에 복사됩니다. 역시 무식하면 저처럼 손발이 고생합니다.
 
 다만 위의 [매크로][1]를 사용해보니 최종 클립보드에 복사된 url이 인코딩이 되지 않았습니다. 위에 링크한 매크로를 사용하시는 경우 퍼센트 인코딩 클립보드 필터 액션을 추가하여 사용하세요. 이 매크로는 Finder를 열어 원하는 파일을 선택한 상태에서 Trigger 하셔야 작동합니다.

 제가 만든 매크로에 따로 단축키는 설정하지 않은 상태이니 원하는 단축키를 설정해서 사용하면 됩니다. 저는 "⌘⌥^ T" 단축키를 사용하여 Trigger by name 패널에 "cdp"라고 입력해서 매크로를 실행하고 있습니다. 편한 방법으로 사용하시기 바랍니다. 이 글에 나온 Keyboard Maestro 매크로와 워크플로우는 아래에서 내려 받을 수 있습니다.

### Keyboard Maestro 매크로와 워크플로우 다운로드 링크

* Copy Dropbox public link url to Clipboard: Keyboard Maestro Macro file(.kmmacros) >> [다운로드][2]
* Copy Public Link: Automator workflow file(.workflow) >> [다운로드][3]
* Dropbox public path to url: Keyboard Maestro Macro file(.kmmacros) >> [다운로드][4]


[1]:https://dl.dropboxusercontent.com/u/18183807/Finder%20macros.kmlibrary
[2]:http://dl.dropboxusercontent.com/u/18183807/Copy%20Dropbox%20public%20link%20url%20to%20Clipboard.kmmacros
[3]:http://dl.dropboxusercontent.com/u/18183807/CopyPublicLink.workflow
[4]:http://dl.dropboxusercontent.com/u/18183807/Dropbox%20public%20path%20to%20url.kmmacros