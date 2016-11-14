---
layout: post
title: FC660C 키 리매핑
date: 2016-11-14 17:23:06
tags: keyboard remapping Karabiner-Elements Keyboard-Maestro
---
맥북에서는 ^ 키와 CapsLock 키만 서로 바꿔쓰면 충분했는데, FC660C에서 fn 키를 못 쓰는 것이 아쉬웠습니다.[^1] 그래서 자주 가는 클리앙의 맥당에 [질문을](http://www.clien.net/cs2/bbs/board.php?bo_table=cm_mac&wr_id=1078462&sca=&sfl=mb_id%2C1&stx=charmjf) 올렸고, Karabiner-Elements 로 FC660C의 Modifier key 매핑을 다시 할 수 있다는 댓글을 보고 적용했습니다.

![](http://dr.halryang.net/52Uv+)

처음엔 위와 같이 적용하니 FC660C에서는 제가 원한대로 작동하지만 맥북의 키보드에서 ⌘ 키와 ⌥ 키가 서로 바뀌는 현상이 생겨 원치 않는 결과가 나왔습니다. 위의 화면에서 세 번째 탭(devices) 에서 기본 키보드는 제외하고 미니 키보드에서만 Karabiner-Elements 를 적용하도록 설정하니 해결되었습니다.

이렇게 하고 나니 이제 외장 키보드를 연결하면 Karabiner-Elements 가 실행되어 위의 세팅을 적용하고, 외장 키보드를 분리하면 Karabiner-Elements 가 종료되면 좋겠다는 생각이 들었는데요. Keyboard Maestro를 이용해서 아래 스크린샷처럼 매크로를 만들었습니다. 

![When FC660C attached](http://dr.halryang.net/cA4M+)

![When FC660C detached](http://dr.halryang.net/cLDv+)

키보드를 분리할 때 Karabiner-Elements를 그냥 종료하거나 강제종료 하는 매크로를 짠 경우에는 Karabiner-Elements가 제대로 종료가 되지 않거나 종료가 되지만 키보드 리매핑 세팅은 변경되지 않았습니다. 그래서 포럼에 글을 올리고 **Found Image and Click** 액션을 사용해보라는 댓글을 적용하니 매크로가 제대로 작동했습니다.

[^1]: 여기서 fn 키는 FC660C에 있는 fn 키가 아니라 맥에서 fn 기능을 하는 키를 말합니다.
