---
layout: post
title: Automator를 이용해서 스크린샷을 Yoink에 넣어보자
date: 2016-01-05 22:26:54
tags: Automator Automation app Yoink workflow productivity
---
[Yoink](https://itunes.apple.com/us/app/yoink/id457622435?mt=12)는 파일 바구니 앱입니다. 갖가지 파일을 담아뒀다가 원하는 곳에 옮길 때 빛을 발하는 앱이죠. 블로그에 올릴 글을 쓰면서 스크린샷을 많이 찍어 공유할 때나 이곳저곳에 흩어져 있던 파일들을 한 폴더에 모을 때 등의 상황에서 요긴하게 쓰입니다.

Yoink 웹사이트[^1]에 갔다가 이전에는 눈여겨 보지 못했던 사용팁[^2]을 봤습니다. Automator를 사용해서 영역 지정 스크린샷을 원하는 폴더에 넣고 Yoink에도 바로 넣을 수 있는 워크플로우를 알게 되었습니다. 개발자가 올린 글[^3]에 보면 어떻게 워크플로우를 만들고 적용하는지 나와있습니다.

## Automator 워크플로우

![](/images/ss_20160105_214053.jpg)

### 서비스 설치하기

1. Automator 워크플로우를 [여기](/assets/Yoink_Screencapture_Workflow.workflow)서 내려받습니다.
2. 내려받은 `.workflow` 파일을 더블 클릭합니다.
3. Install 을 눌러 설치합니다. (스크린샷이 저장될 폴더를 지정하거나 파일명 형식을 지정하시려면 `Open with Automator` 를 누릅니다.)
4. 위의 과정을 거치면 워크플로우가 `~/Library/Services/` 폴더에 설치됩니다.
5. 설치가 잘 되었는지 확인하려면 파인더(Finder) 의 메뉴바에서 Services를 선택하고 Capture Screenshot to Yoink 라는 서비스가 목록에 있는지 봅니다.
6. 원글에서는 `~/Documents/` 폴더에 Yoink 라는 이름의 폴더가 생성되고 이 워크플로우를 사용해서 찍은 스크린샷이 저장됩니다. 하지만 제가 올린 버전은 제가 원래 스크린샷 폴더로 사용하던 `~/Pictures/Capture/` 폴더에 스크린샷을 저장합니다.

여기까지 하셨으면 영역을 지정해서 찍은 스크린샷을 `~/Pictures/Capture` 폴더에 넣고 Yoink에 담는 서비스를 잘 설치했습니다. 이제 조금 더 편하게 사용하기 위해서 키보드 단축키를 설정해볼까요?

### 키보드 단축키 설정하기

1. 시스템 환경설정을 엽니다.
2. 키보드 → 단축키 → 서비스 순서로 들어갑니다.
3. 서비스 목록 General 아래에서 Capture Screenshot to Yoink 를 찾습니다.

![](/images/ss_20160105_213328.jpg)

단축키 추가를 누르고 원하는 단축키를 설정하면 끝입니다. 저는 기본 단축키인 `⇧⌘4`를 이 워크플로우로 지정했습니다. 기본 단축키를 이 워크플로우에 지정하려면 위의 `Screen Shots`에서 기본으로 지정된 단축키를 해제하고 나서 지정해야 합니다.

### 개인의 환경에 맞게 바꿔서 사용하세요

원글에 있는 팁을 참고해서 저는 제가 원하는 대로 약간 수정해서 사용하고 있습니다. 대단히 복잡한 것을 바꾼 것은 아니고, 생성되는 스크린샷 파일을 저장할 폴더를 바꾸고 생성되는 파일명의 형식을 바꾸는 정도입니다.

#### 파일명을 입맛대로

![](/images/ss_20160105_173718210.png)

사각형 안에 보이는 부분이 제가 바꾼 부분입니다. 스크린샷임을 바로 알 수 있도록 앞에 `ss_`를 붙이고 스크린샷을 찍는 날짜를 그 뒤에 `yyyymmdd_` 형식으로 오도록 했습니다. 마지막으로 시간을 `hhmmss`형식으로 넣고 `.jpg` 확장자로 마칩니다.

#### 스크린샷을 저장할 폴더 설정하기

![](/images/ss_20160105_214259.png)

위의 스크린샷에서 사각형으로 표시한 부분에 원하는 폴더 경로를 넣어주시면 됩니다. 네, 간단합니다. 

### One More Thing?

지금까지 설명한 워크플로우는 기본적으로 영역을 지정하게 되어 있습니다. 그런데 깔끔하게 윈도우 창을 스크린샷으로 담고 싶은 경우도 많습니다. 그래서 아주 약간의 수정을 해서 워크플로우를 하나 더 만들었습니다. 이 워크플로우는 윈도우를 선택해서 스크린샷을 찍고 Yoink에 담아줍니다. 위에 단축키를 설정하는 스크린샷에서 이미 보신 분도 계시지요? [여기](/assets/Yoink_win_Screencapture_Workflow.workflow)에서 내려받을 수 있습니다. 설치하여 사용하는 방법은 위에서 설명드린 것과 같습니다.

### 맺으며

좋은 앱을 더 효율적으로 사용할 수 있는 방법을 찾아서 적용하는 것은 언제나 재밌습니다. 저는 Automator도 모르고 Applescript, shell script 모두 모릅니다. 구글링을 통해 조금씩 바꿔보는 것이라서 어설픕니다. 이것보다 더 좋은 방법으로 워크플로우를 수정하셔서 사용하실 아이디어가 있으신 분은 제게도 알려주세요. :)

[^1]: [Yoink](http://eternalstorms.at/yoink)

[^2]: [Yoink - Usage Tips](http://eternalstorms.at/yoink/Yoink_-_Draggings_a_drag_no_more/Yoink_-_Usage_Tips.html)

[^3]: [Capture Selective Screenshots in Yoink with Automator](https://eternalstorms.wordpress.com/2015/01/15/capture-selective-screenshots-in-yoink/)
