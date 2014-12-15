---
layout: post
title: 마크다운 입력을 편하게 해주는 Keyboard Maestro 라이브러리 소개
tags: Keyboard-Maestro
published: True
---

[Keyboard Maestro][7591-0001]의 매크로는 맥의 어떤 앱에서나 적용이 가능하므로 한 번 Keyboard Maestro으로 마크다운을 쓰는 데에 익숙해지면, 자신이 사용하는 문서 편집 앱이 무엇이든 마크다운을 편하게 쓸 수 있습니다. 전 맥에서 [nvALT][7591-0002], [Byword][7591-0003], [Sublime Text 3][7591-0004]까지 쓰는 중이고 이 모든 앱에서 마크다운을 사용하고 있습니다. 각각의 앱에서 글을 쓰는 환경이 다름에도 어디서나 제가 손에 익은 방법을 이용해서 마크다운을 쓸 수 있는 것은 상당히 큰 장점입니다. OS X의 거의 모든 앱에서 비슷한 메뉴 항목을 제공해서 "환경설정" 항목이 어디 있는지 한참을 찾지 않아도 되는 것도 **동일한 사용자 경험**을 유지하는 것이 사소한 것에서 큰 만족을 주는 예입니다.

[km-markdown-library](https://github.com/Zettt/km-markdown-library "km-markdown-library")를 소개합니다. 이 Keyboard Maestro library는 마크다운을 사용하는 데 자주 쓰이는 많은 기능을 보다 편하게 사용할 수 있도록 도와줍니다. 이 라이브러리에 포함된 매크로들은 보통 `^⌥ + 키`의 단축키를 이용합니다. 예를 들어 글씨 특성을 적용하고 싶은 텍스트를 선택한 후 `^⌥i`로 "이탤릭체", `^⌥b`로 "굵게"를 적용하는 매크로를 사용할 수 있습니다.

지원하는 매크로는 아래와 같습니다.

* **Format**: Italic, Bold, Wrap in "", Wrap in (), Wrap in [], Wrap in ``, Make Quote, 위첨자, 아래첨자
* **Manipulate**: Indent Text, Outdent Text, Header, List(Unordered, ordered)
* **Insert**: Image, Footnote
* **Process**: Preview Selection, Convert Selection, Markdownify
* **Cleanup**: Cleanup Table, Force Line Break, Remove Formatting, formd
* **Personal**: Insert Chapter Reference
* **Help**: Multimarkdown Syntax, markdown for KM Guide
* **Markdown Link**: New Link, Link List from Clipboard, Link Inlines to References

다만 지금 Sublime Text 3에서는 한글을 감싸는(wrap) 매크로를 실행하면 선택한 텍스트의 자소가 분리되어 보이는 버그가 있습니다. 다른 앱을 사용하는 경우에는 자소분리현상을 보지 못 했고, Sublime Text 3 상에서 자소가 분리되어 보여도 눈에 그렇게 보이는 것이고 다른 앱에서 해당 파일을 불러오면 한글이 제대로 보이고 이탤릭, 굵게 등 글자 속성도 잘 적용되어 있습니다. 그래도 Sublime Text 3에서는 글자가 분리되어 보이는 것이 영 보기에 좋지 않습니다.

저는 Sublime Text 3에서는 km-markdown-library중 wrap 매크로에 해당하는 부분은 사용하고 있지 않습니다. 그래도 Heading을 넣거나 리스트 항목을 주욱 적고 나서 선택하여 목록 형태를 만드는 등 마크다운을 편하게 이용하는 데 큰 도움이 되어 가장 잘 쓰는 Keyboard Maestro Macro 라이브러리여서 소개했습니다. Keyboard Maestro와 마크다운을 모두 사용하는 분이 계시다면 평소 쓰시는 문서 편집 앱에 관계없이 한번쯤 내려받아 써보실 것을 권장합니다.

[7591-0001]: http://www.keyboardmaestro.com/
[7591-0002]: http://brettterpstra.com/projects/nvalt/
[7591-0003]: http://bywordapp.com/
[7591-0004]: http://www.sublimetext.com/3


<!-- Report:
(7:0:29): [Keyboard Maestro](!s) => http://www.keyboardmaestro.com/
(7:148:18): [nvALT](!s) => http://brettterpstra.com/projects/nvalt/
(7:168:19): [Byword](!s) => http://bywordapp.com/
(7:189:27): [Sublime Text 3](!s) => http://www.sublimetext.com/3
(): Processed: 5 links, 0 errors.
-->