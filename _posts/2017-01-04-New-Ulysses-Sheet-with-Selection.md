---
layout: post
title: 선택한 텍스트로 Ulysses에 새로운 시트 만들기
date: 2017-01-04 12:00
tags: Ulysses
---

Ulysses는 [x-callback-url을 지원][1]하기에 선택한 텍스트로 Ulysses에 새로운 시트를 작성할 수 있습니다. 한글을 선택해서 보내는 경우 인코딩을 하지 않으면 물음표만 나옵니다. [여기][2]를 참고해서 파이썬으로 인코딩해서 보내는 스크립트를 짜고 해당 스크립트를 실행하는 서비스를 만들었습니다. 텍스트를 선택하고 서비스를 실행하면 Ulysses가 실행되고 새로운 시트에 선택한 텍스트가 들어갑니다. 서비스에 단축키를 설정하면 더욱 편하게 사용할 수 있습니다.

[New Ulysses Sheet with Selection 서비스 다운로드][3]

### [ PopClip][4] 사용자를 위한 보너스

위의 서비스를 내려받고 [여기][5]에서 Send to Ulysses.popclipext를 내려받아 설치하시면 선택한 텍스트를 PopClip을 통해서 Ulysses로 보낼 수 있습니다.

[1]:	https://ulyssesapp.com/blog/2016/04/introduction-x-callback-support/
[2]:	http://ecolemodev.wikinamu.com/%ED%8C%8C%EC%9D%B4%EC%8D%AC#header-2-2
[3]:	http://dr.halryang.net/1fcHJ
[4]:	http://pilotmoon.com/popclip/
[5]:	http://dr.halryang.net/x1Xz

