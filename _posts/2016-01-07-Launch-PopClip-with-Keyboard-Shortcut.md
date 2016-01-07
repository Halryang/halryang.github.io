---
layout: post
title: 키보드 단축키로 PopClip를 실행하기
date: 2016-01-07 14:52:18
tags: PopClip app script productivity
---
마우스나 트랙패드를 쓰고 있을 때 유용한 [PopClip](https://pilotmoon.com/popclip/)을 키보드를 사용할 때도 마우스나 트랙패드로 손을 옮기지 않고 사용할 수 있도록 서비스를 만들었습니다. 아쉬운 것은 PopClip 글을 입력하는 곳이나 선택한 텍스트 근처가 아닌 마우스 포인터 위로 PopClip이 실행되는데요. 이게 약간 이질감이 들 수 있습니다. 하지만 PopClip 바(?)가 나오는 위치를 바꾸는 것은 제 능력 밖이라 포기했습니다.

![](/images/ss_20160107_140311.jpg)

Automator로 서비스 만들기로 만들었고, 아주 간단한 AppleScript를 실행하는 것이 끝입니다.

![](/images/ss_20160107_140354.jpg)

시스템 환경설정 → 키보드 → 단축키에서 원하시는 단축키를 지정해서 사용하시면 됩니다. 저는 `^P`로 지정했습니다.
