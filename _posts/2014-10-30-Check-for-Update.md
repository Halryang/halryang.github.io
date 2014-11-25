---
layout: post
title: Check for Update - Keyboard Maestro Macro
date: 2014-10-30 15:35:20
tags: Keyboard-Maestro
---


요즘 거의 모든 앱은 자동으로 업데이트가 있는지 확인하는 기능이 있다. 그래도 앱을 사용하다 보면 지금 사용하고 있는 버전이 가장 최신 업데이트 버전인지 확인하고 싶은 때가 있다. 그때마다 메뉴로 커서를 옮겨서 업데이트를 확인하기 귀찮아서 매크로를 만들었다.

![Check for Update - Keyboard Maestro Macro](http://dl.dropboxusercontent.com/u/18183807/wp/CUkmm.jpg "Check for Update - Keyboard Maestro Macro")

단순하다. 맥에서 사용하는 거의 모든 앱이 화면의 왼쪽 위에 한 입 베어 문 사과 모양 아이콘의 바로 오른쪽에 해당 앱의 이름으로 된 메뉴를 제공한다. 보통 이 메뉴를 클릭해서 아래로 펼쳐지는 항목 중 "Check for update..."을 눌러서 최신 업데이트 버전인지 확인한다.

그래서 이 매크로는 사과 아이콘 바로 우측 지점을 마우스 클릭하고 키보드 "C"키를 눌러 "Check for update..."항목을 선택한 후 ↩키를 누르도록 설정했다.

물론 매크로가 단순한 만큼 한계가 있다. OS X에서 기본으로 제공하는 사파리, 메일, 메시지 등의 앱처럼 메뉴에 "Check for update..." 항목이 없는 경우 이 매크로가 제대로 작동하지 않는다. 하지만 이런 기본 제공 앱에서 따로 업데이트를 확인할 일이 없고, 다른 대부분의 앱에서는 제대로 작동한다.