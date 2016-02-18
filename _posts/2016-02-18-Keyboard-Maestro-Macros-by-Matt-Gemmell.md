---
layout: post
title: Keyboard Maestro Macros by Matt Gemmell
date: 2016-02-17 17:26:29
tags: Keyboard-Maestro
---
[Keyboard Maestro][]를 사용하지만 아직 그 기능을 모두 쓰지는 못하고 있습니다. 능력자분들은 더 편하게 좋은 매크로를 짤 수 있겠지만 저는 능력자가 아니라서요. 능력자 중 한 명인 [Matt Gemmell](http://mattgemmell.com/about/)이 블로그에 올린 글 중 Keyboard Maestro 매크로를 내려받을 수 있도록 제공하는 [글](http://mattgemmell.com/keyboard-maestro-macros/)을 소개합니다. 많은 유용한 매크로를 소개하고 있는데, 설명을 보시고 필요한 것을 받아서 쓰면 되겠습니다. 키보드 단축키가 이미 할당되어 있는 경우에도 원하는 트리거 옵션으로 바꾸어 사용하실 수 있습니다.

### 사파리

사파리에서 활성화 되어 있는 탭/창의 URL에 동작하는 매크로 4개입니다. URL의 숫자 파라미터를 찾아서 그것을 1 혹은 10 단위로 증감하고, 페이지를 새로고침 합니다. 기본적으로 키보드 단축키가 할당되어 있습니다. 이 매크로들은 온라인 갤러리, 다수의 페이지로 나누어진 기사 등을 보는데 유용합니다.

[사파리 매크로 내려받기](http://mattgemmell.com/files/keyboard-maestro/safari-macros.zip)

### 메일

이 매크로는 이메일에 답장을 보낼 때 `hisender`("hi sender") 라고 입력하면 아래처럼 발신자의 이름이 들어간 기본적인 인사말이 들어가도록 합니다.

> Hi [Firstname],  
> Thanks for your message.

기본적으로 위의 인사말이 입력되는 지점은 가장 마지막으로 입력한 문장의 바로 다음에 들어갑니다. 이메일에 답장할 일이 많고, 항상 쓰는 문장이 있다면 원하는 문구로 약간 수정해서 사용하면 되겠습니다.

[메일 매크로 내려받기](http://mattgemmell.com/files/keyboard-maestro/mail-macros.zip)

### 파인더

이 매크로는 Andrew Burgess가 만든 것을 Matt Gemmell이 약간 수정한 버전입니다. 이 매크로는 파인더에서 선택한 파일을 당신의 Dropbox 퍼블릭 폴더로 이동하고 공유 링크를 클립보드에 복사합니다.

매크로를 사용하려면 스크립트 안의 URL을 당신의 고유 Dropbox public ID로 바꾸어야 합니다. 고유 Dropbox public ID는 Dropbox 웹 인터페이스에서 확인할 수 있습니다. Dropbox 폴더를 기본 경로 외에 다른 경로로 지정해서 사용하고 있다면 스크립트 안에서 Dropbox 폴더 경로도 바꿔야 합니다.

[파인더 매크로 내려받기](http://mattgemmell.com/files/keyboard-maestro/finder-macros.zip)

### 앱과 함께 볼 노트 작성

이 매크로들을 사용하면 현재 사용하고 있는 (가장 앞에 활성화 되어 있는) 앱이 실행될 때 볼 노트를 작성할 수 있습니다. 다음에 해당 앱을 실행하면, 자동으로 이 매크로로 작성한 노트가 나옵니다. 앱을 통해 어떤 일을 하고 있었는지, 혹은 다음에 어떤 작업을 할 것인지 적어두면 매우 편리합니다.

![](https://farm2.staticflickr.com/1663/24806086236_41e723fd60.jpg)

* 현재 사용중인 앱의 노트를 수정하려면, `^N`을 누르면 됩니다.
* 노트 창의 저장 버튼을 누르는 대신 `⌥↩`을, 삭제 버튼을 누르는 대신 `⌥D`를 사용할 수 있습니다.

이 매크로로 작성한 노트는 플레인 텍스트 파일로 저장됩니다. 노트 파일은 `~/Library`안의 `Keyboard Maestro의 `Application Support`폴더 내에 `AppSpecificNotes` 폴더에서 찾아볼 수 있습니다. 이 매크로들은 Keyboard Maestro 버전 7 이후 버전에서만 작동합니다.

[앱과 함께 볼 노트 작성 매크로 내려받기](http://mattgemmell.com/files/keyboard-maestro/app-specific-notes.zip)

### Heads-Up Info Display

이 매크로를 실행하면 팝업 창으로 달력, 시간, 날짜, 맥북을 사용하는 경우 맥의 배터리 상태를 알려줍니다. 이 매크로를 실행하는 기본 단축키는 `^⌥-`로 설정되어 있습니다.

![](https://c2.staticflickr.com/2/1549/24595574079_d2b2842b67_z.jpg)

설치와 사용방법은 내려받은 폴더에 포함된 "'HOW TO USE" 파일의 내용을 참고하시면 됩니다. 설정은 매우 단순합니다. 필요한 설정을 하고 매크로를 실행해야 합니다. 이 매크로는 Keyboard Maestro 버전 7 이후 버전에서만 작동합니다.

[Download Heads-Up Info Display macro](http://mattgemmell.com/files/keyboard-maestro/heads-up-info-display-macro.zip)

### 파일 아이콘 매크로

이 매크로는 커스텀 HTML 프롬프트 창에서 파일이나 폴더, 혹은 앱의 아이콘을 어떻게 사용하는지 보여줍니다. 기본 단축키는 `^⌥T`로 설정되어 있습니다.

설치와 사용방법은 내려받은 폴더에 포함된 "'HOW TO USE" 파일의 내용을 참고하시면 됩니다. 설정은 매우 단순합니다. 필요한 설정을 하고 매크로를 실행해야 합니다. 이 매크로는 Keyboard Maestro 버전 7 이후 버전에서만 작동합니다.

[파일 아이콘 매크로 내려받기](http://mattgemmell.com/files/keyboard-maestro/file-icon-test-macro.zip)

### 글로벌

* 메인화면의 정중앙에 마우스 위치시키기. 매크로 이름 그대로 작동합니다. 그리고 커서를 잠시 하이라이트 합니다.
* 알림 지우기. 이 매크로는 알림 센터에 알림을 지우기 위해 마우스를 움직여 '닫기' 버튼을 클릭합니다. 더블 클릭을 하도록 설정되어 있는데, 한 번만 클릭하는 경우 제대로 작동하지 않는 경우가 있어서 그렇게 했다고 합니다.[^1]
* Front window to image on Desktop. 이 매크로는 가장 앞에 있는 창의 스크린샷을 찍고, 파일명을 물어본 다음, 사용자의 바탕화면에 PNG 파일로 저장합니다.
* Right-click in frontmost window. 키보드에서 손을 떼기 싫어서 만든 매크로랍니다. 이 매크로는 가장 앞에 있는 창의 가운데이 우클릭시 나타나는 메뉴가 나타나도록 합니다. 원한다면 현재 커서 위치에 메뉴가 나오도록 수정하여 사용할 수 있습니다.
* Type clipboard. 클립보드에 복사된 내용을 한 글자씩 타이핑하는 매크로입니다. 암호를 입력하는 곳 등 붙여넣기가 불가능한 곳에 사용할 수 있습니다.

[Download Global macros](http://mattgemmell.com/files/keyboard-maestro/global-macros.zip)

여기까지가 지금까지 Matt Gemmell이 공유하고 있는 Keyboard Maestro Macro들 입니다. 제가 처음 이 글을 본 것은 2014년이었는데, 새롭게 추가되는 매크로들도 있으니 [원문](http://mattgemmell.com/keyboard-maestro-macros/)을 즐겨찾기에 넣어두시고 가끔 들여다 보시는 것도 좋겠습니다.

[^1]: 저는 이 매크로는 아예 작동하지 않습니다. 원인이 무엇인지는 잘 모르겠습니다.

[Keyboard Maestro]: http://www.keyboardmaestro.com/
