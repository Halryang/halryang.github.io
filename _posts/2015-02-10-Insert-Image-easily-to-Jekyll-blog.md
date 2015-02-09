---
layout: post
date: 2015-02-10 12:42:37
title: 지킬 포스트에 이미지를 쉽게 삽입하는 Keyboard Maestro Macro
tags: Keyboard-Maestro productivity automation blogging jekyll
---

지금 여러분이 보고 계신 블로그는 [지킬](http://jekyllrb-ko.github.io/ "Jekyll • 심플하고 블로그 지향적인 정적 사이트")로 만든 블로그입니다. 저는 지킬 블로그를 참 만족하면서 이용하고 있습니다. **가볍고 빠르고**, 제가 원하는 에디터를 사용해서 글을 작성해 올릴 수 있다는 장점도 있습니다. 게다가 [GitHub Pages](https://pages.github.com/ "GitHub Pages")를 이용해서 호스팅을 받으니 **무료**입니다. 하지만 모든 것이 좋을 수는 없지요. 마크다운으로 글을 작성하면서 이미지를 넣는 작업은 영 불편합니다. 워드프레스 블로그에 글을 올릴 때는 글쓰기 앱으로 드래그 앤 드랍으로 이미지를 삽입하고 미리보기 및 간단한 편집까지도 가능합니다. 이렇게 넣은 이미지는 워드프레스로 글을 발행할 때 저절로 업로드되니 매우 편리합니다. 이 정도 수준은 아니더라도 지킬에 발행할 글에 이미지를 좀더 편하게 넣을 수 있으면 좋겠다고 생각했습니다.

이전에 Dropbox에 파일을 올리고 공개링크를 얻었던 것[^1]이 떠올랐습니다. 이걸 조금만 다듬으면 지킬 포스트에 이미지를 삽입하는 것이 편해지겠다는 생각이 들었지요. 그래서 두 개의 Keyboard Maestro Macro를 지킬에 맞도록 만들었습니다.

### 어디서나 실행할 수 있는 매크로
이 매크로([내려받기 링크](http://dl.dropboxusercontent.com/u/18183807/Copy%20Jekyll%20Image%20markdown%20link.kmmacros))는 [LaunchBar][7011-0001]가 필요합니다.[^2] 워크플로우를 내려받고[^3] Workflow 파일의 위치와 파일을 이동할 목표지점(여러분의 지킬 이미지 폴더)을 지정하시고 사용하세요. 이 매크로는 Downloads 폴더에 있는 이미지 파일을 옮긴다고 가정하고 만들었습니다. 고로 중간에 클립보드 문자열을 찾아 바꾸는 부분을 필요에 따라 변경해서 쓰시면 됩니다.

자신의 환경에 맞도록 세팅하고 아무곳에서나 이미지를 삽입하고 싶은 때에 매크로를 실행하면, 이미지 파일을 선택하는 창이 열립니다(Automator Workflow가 처음에 이미지 파일 선택 창을 여는 역할을 합니다). 이제 넣고 싶은 이미지를 선택하면 미리 지정한 로컬 지킬의 이미지 폴더에 파일을 복사하고 마크다운 이미지 링크를 클립보드에 넣어줍니다. 이미지를 선택한 이후 링크가 복사되었다는 알림이 뜨면 원하는 곳에 `⌘+V`로 클립보드에 저장된 링크를 붙여넣기만 하면 됩니다.

### 파인더에서 이미지를 선택한 후 매크로 실행
Matt Gemmell의 매크로를 수정한 버전([내려받기 링크](http://dl.dropboxusercontent.com/u/18183807/Jekyll%20image%20file%20and%20get%20link%20copy.kmmacros))은 파인더에서 이미지를 선택한 상태에서 매크로를 실행하면 이미지 파일을 지킬 폴더로 이동[^4]하고 마크다운 이미지 링크를 클립보드로 복사합니다. 매크로를 받으시면 매크로 안에 있는 AppleScript에서 `Your:Jekyll:Folder:images:`를 사용하고자 하는 지킬 이미지 폴더로 바꿔주세요. 여기서는 폴더 계층 사이에 `/` 대신 `:`를 사용합니다. 나머지 작업은 `⌘+V`로 클립보드에 저장된 링크를 붙여넣기만 하면 됩니다.

아래는 제가 테스트 용도로 무작위로 올려 본 이미지 링크입니다.

![](/images/1280px-Dr_Jekyll_and_Mr_Hyde_poster_edit2.jpg)
![](/images/848739290_52a4d43225_b.jpg)
![](/images/4868556779_d0ddb0b03d_b.jpg)

이 매크로로 지킬에 이미지를 넣는 작업이 조금 더 편해질 것 같습니다. 더욱 빠르고 간결하게 이미지를 삽입하는 방법을 아시는 분은 블로그 하단에 제 이메일, 트위터가 링크되어 있으니 팁을 공유해주세요. 감사합니다. :)

[^1]: 이전 글 링크: [Dropbox의 공개 링크를 쉽게 얻자](http://halryang.net/getsharableurl/ "Copy Dropbox public link url to Clipboard - Keyboard Maestro Macro")

[^2]: 물론 [LaunchBar][7011-0001]가 없이도 실행할 수 있는 방법이 있을 것 같지만, 제가 만들 능력이 없습니다.

[^3]:  워크플로우 내려받기 링크: [Copy File Path - Automator Workflow link](http://dl.dropboxusercontent.com/u/18183807/CopyFilePath.workflow)

[^4]: 위의 매크로는 복사 후 붙여넣지만 이 매크로는 파일을 이동합니다. 원본 파일이 이동한다는 것을 염두하고 사용하세요.

[7011-0001]: http://www.obdev.at/products/launchbar/
