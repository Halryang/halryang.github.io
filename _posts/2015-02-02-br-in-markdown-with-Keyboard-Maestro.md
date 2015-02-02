---
layout: post
title: Keyboard Maestro Macro를 사용해서 마크다운 강제 줄 바꾸기
date: 2015-02-02 23:02:00
tags: Keyboard-Maestro mac app tip Byword markdown
---

저는 주로 [Byword][9412-0001]를 OS X 마크다운 에디터로 사용하고 있습니다. Byword가 마크다운을 잘 지원하지만, HTML에서 `<br>`에 해당하는 강제 줄 바꿈을 할 수 있는 키보드 단축키는 없습니다. 마크다운 문법을 사용할 때 스페이스 두 번을 입력하고 다음 줄에 글을 쓰면 강제 개행을 할 수 있습니다. 이게 한 번 쓰는 데에는 그다지 불편함이 없어도, 상당히 많은 강제 개행을 해야하는 경우에는 꽤나 불편합니다. Keyboard Maestro Macro를 사용해서 조금 더 편하게 강제 개행을 하는 방법을 소개하겠습니다.

## Force Line Breaks
[이전에 소개한](http://halryang.net/keyboard-maestro-for-markdown/) Keyboard Maestro 매크로 라이브러리에 포함된 **Force Line Breaks** 매크로를 이용하는 방법이 있습니다. 이 방법을 사용할 때엔 강제 개행이 필요한 글을 먼저 그냥 리턴키를 사용해서 작성한 후 그대로 개행을 유지하고 싶은 영역을 선택한 상태에서 Force Line Breaks 매크로를 실행하면 됩니다. 이 매크로는 선택한 영역 안에 줄바꿈이 된 부분에 스페이스바를 두 번 삽입합니다. 그 결과, 줄바꿈이 된 곳은 강제 개행이 적용되지요.

## Shift + ↩ 키를 사용
![Screen shot of br code Keyboard Maestro Macro](/images/ssBRkmm.png)
가끔은 위의 방법을 사용하는 것보다 Shift + ↩ 키를 사용해서 강제 개행을 하는 것이 더 편할 때가 있습니다. 다른 편집기에서 익숙하게 썼던 단축키가 Shift + ↩ 이었기에 전 이렇게 설정했지만 다른 것이 더 손에 익으신 분은 다른 단축키를 지정하셔도 됩니다. 이 매크로를 활성화하고 강제 줄바꿈을 원하는 때에 Shift + ↩ 을 누르면 스페이스바를 두 번 누른 공백을 넣고 줄바꿈을 합니다. 전 Byword에서만 활성화되도록 설정했습니다.

## 맺으며
마크다운에서 강제 줄 바꿈을 좀 더 간단하게 하는 Keyboard Maestro Macro를 소개했습니다. 더 좋은 방법을 아시는 분 계신지요? 더 좋은 팁을 아시는 분은 제게도 알려주세요. 우리 모두 나날이 더 즐겁게 글을 쓸 수 있기를 바랍니다.

[9412-0001]: http://bywordapp.com/


<!-- Report:
(7:6:19): [Byword](!s) => http://bywordapp.com/
(): Processed: 3 links, 0 errors.
-->