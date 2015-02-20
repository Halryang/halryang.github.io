---
layout: post
date: 2015-02-20 11:52:44
title: 매크로 이름으로 Keyboard Maestro Macro를 실행하는 방법
tags: LaunchBar Keyboard-Maestro productivity automation app macro
---

[Keyboard Maestro][8752-0001]는 키보드를 사랑하는 제게는 축복과도 같은 어플입니다. 단축키를 사용하면 다양한 상황에서 트랙패드 혹은 마우스를 이용해서 하는 것보다 많은 시간을 절약할 수 있습니다. 단축키를 애용하시는 분은 제가 하는 말의 의미를 아시겠지요. 하지만 많은 매크로에 일일히 단축키를 적용하기도 힘들고, 그 많은 단축키를 외우는 것도 힘듭니다. 그래서 저는 Keyboard Maestro Macro를 만들 때 적당한 이름을 설정하고 나중에 사용할 때에는 매크로 이름으로 검색해서 사용하는 방법을 많이 사용하고 있습니다.

### LaunchBar에서 Keyboard Maestro Macro를 실행하자

[LaunchBar][8752-0002]와 Keyboard Maestro는 제가 맥 앞에 있을 때면 언제나 백그라운드에서 돌아가는 어플입니다. LaunchBar는 키보드 런처 앱의 원조입니다. 오랜 시간이 흐르면서 쌓인 노하우는 부드러운 사용자 경험으로 이어집니다. LaunchBar의 개발사인 Objective Development에서는 LaunchBar 6 액션을 공유할 수 있는 포럼[^1]을 운영하고 있습니다. 지금 소개하려는 LaunchBar 액션도 이 포럼에서 찾았습니다.

지금 설명할 Keyboard Maestro Macro를 검색하고 실행하는 LaunchBar 액션은 LaunchBar 포럼[^2]에서 내려받을 수 있습니다. LaunchBar를 실행한 후 `KMM`이라고 입력하면 이 액션이 선택되고 스페이스바를 누르면 Keyboard Maestro에 등록된 모든 매크로가 뜹니다. 물론 이 목록을 화살표로 움직이면서 선택해야 하는 것은 아닙니다. 원하는 매크로 이름의 일부만 적으면 실시간으로 매크로의 목록이 추려집니다. 구글의 인스턴트 검색 기능처럼요.

각 매크로를 직접 Launchbar 창에서 간단히 불러올 수 있으면 좋겠지만 Launchbar에서 Keyboard Maestro의 매크로를 인덱싱하는 게 아니라서 그건 불가능하다고 하네요. 지금 소개한 액션 말고도 많은 유용한 액션들이 이미 공유되고 있으니 LaunchBar 6를 쓰고 계신 분은 포럼을 둘러보시길 권합니다.

### Keyboard Maestro 안에서 해결하자
![](/images/ss-kmm-search-by-macro-name.png)

위에서 설명한 LaunchBar 액션을 사용하지 않고도 편하게 Keyboard Maestro Macro를 선택하는 방법이 있습니다. Keyboard Maestro은 매크로 이름으로 매크로를 검색하는 기능을 기본으로 제공합니다. 당연히 단축키를 사용해서 이 창을 불러올 수 있고, 전 ⌥+스페이스바 키를 이용해서 사용하고 있습니다. 저는 LaunchBar가 손에 익고 보기 좋아서 위의 방법을 많이 사용하지만, 이 방법도 상당히 깔끔하고 부드럽습니다. 위의 방법보다 조금 덜 손가락을 움직이고 매크로를 실행할 수 있기도 합니다. 물론 LaunchBar를 사용하지 않고 Keyboard Maestro만 쓰시는 분은 이 방법을 사용하시면 되고, LaunchBar와 Keyboard Maestro 모두 쓰시는 분은 둘 중에 더 마음에 드는 방법을 택해서 사용하시면 됩니다.

더 편하게 Keyboard Maestro를 사용하는 방법을 아시는 분이 계시지요? 제게도 팁을 나누어 주세요. 고맙습니다. :)

[8752-0001]: http://www.keyboardmaestro.com/
[8752-0002]: http://www.obdev.at/products/launchbar/


[^1]: [Objective Development Forums • View forum - LaunchBar Actions](http://forums.obdev.at/viewforum.php?f=24)

[^2]: [Objective Development Forums • View topic - [LB6 Action] Keyboard Maestro Macros](http://forums.obdev.at/viewtopic.php?f=24&t=9079&sid=3b76d13ac37c3ee3742bf1add484e19a)


