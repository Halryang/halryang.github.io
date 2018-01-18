---
layout: post
title: Writng on Emacs for jekyll blog
date: 2018-01-18 17:35:51
tags: Emacs jekyll blogging
---

새해 들어서 Emacs를 써보기 시작하면서 이것으로 지킬 블로깅도 할 수 있을지 궁금해졌습니다. Emacs의 강력한 기능은 제가 잘 알지도 못하니 간단히 글을 적는 것으로 사용할 수 있는데요. 저는 글을 많이 적는 것도 아니고 어찌 보면 블로그에 글을 적는 것이 일기 외에는 유일한 글 적는 곳이니까요. 일단 마크다운으로 글을 적는 것은 플레인텍스트 기반이기에 어느 앱을 사용해도 무리가 없습니다. Emacs는 간단하게 글을 적고 바로 Magit을 이용해서 GitHub에 Publish까지 할 수 있을 것 같습니다. 글을 적는 앱이 따로 있고 또 터미널을 열어서 git commit, push를 해야 하는 것을 한 곳에서 할 수 있다는 장점이 있지요. 다만 그것을 제대로, 편하게 하기 위해서는 조금 배움이 필요한 것 같습니다.

## 부딪힌 문제들 ##

### 한글 자소가 분리되어 나오는 증상 ###

Emacs에 있는 자체 입력기를 사용하는 것으로 해결할 수 있습니다. 저는 Keyboard Maestro로 Emacs를 활성화할 때 macOS 자판을 항상 영어 자판으로 설정하도록 하고, Emacs 내부의 입력기를 사용하는 것으로 세팅했습니다.

![Activate Emacs with English keyboard layout](https://cl.ly/1q1c173F1S2F/Image%202018-01-18%20at%205.54.41%20PM.png "screenshot of Keyboard Maestro Macro for Emacs activation")

```
;; Korean Setting
(package-initialize)

(set-language-environment "Korean")
(setq default-korean-keyboard "3")
(setq input-method-verbose-flag nil input-method-highlight-flag nil)
(prefer-coding-system 'utf-8) ; utf-8 환경 설정
```

### Alfred snippets 사용 불가 ###

기존에 사용하던 Alfred snippet이 Emacs에서는 작동하지 않는데, 이것은 아마 Paste 형식으로 snippet 확장이 일어나기 때문인 것 같습니다. Keyboard Maestro에서 "Insert Text by Typing"으로 만든 스니펫은 잘 작동합니다. Emacs에서는 Keyboard Maestro를 사용하거나 필요한 스니펫은 YASnippet이라는 Emacs의 스니펫 기능을 사용할까 생각중입니다.

```
;;yasnippet
(use-package yasnippet
  :ensure t
  :config
  (yas-global-mode 1))
```

### macOS 클립보드와 연동 문제 ###

시스템 클립보드에 복사하거나 오려둔 텍스트를 Emacs에 붙여넣지 못하는 문제가 있었습니다. 구글링을 통해 `(setq save-interprogram-paste-before-kill t)`를 `.emacs` 파일에 넣는 것으로 해결했습니다.

## 이제 Emacs에서 글을 적어보자 ##

### markdown-mode on Emacs ###

저는 거의 모든 플레인텍스트 글쓰기에 마크다운을 사용하고 있습니다. 당연히 Emacs에서도 마크다운을 편하게 사용할 수 있는 모드가 있을 것이라 생각하고 검색해서 찾았습니다. [Markdown-mode project source](https://jblevins.org/projects/markdown-mode/ "markdown-mode")를 참고해서 Emacs에 markdown-mode를 넣었습니다. 제가 주로 사용하는 마크다운의 기능은 이미 아주 충분히 구현되어 있습니다. 주로 사용할 기능들을 아래 리스트에 정리했습니다.

- `C-c-l`: insert markdown link
- `C-c-i`: markdown insert image
- `C-c-s C`: insert a GFM style backquote fenced code block
- `C-c-s f`: insert footnotes
- `C-c-o`: Following links
- Editing Lists: `M-RET`, `C-c UP`, `C-c DOWN`, `C-c LEFT`, and `C-c RIGHT`
    - 새로운 리스트 항목, 포인트가 위치한 항목을 위 아래로 이동, 항목을 들여쓰기/내어쓰기
- Shifting the Region: `C-c <` and `C-c >`
- Killing Elements: `C-c-k`
- Outline Navigation: 
    - `C-c-n`, `C-c-p`: 다음/이전 headings/리스트 항목으로 이동(레벨 무관)
    - `C-c-f`, `C-c-b`: 다음/이전 headings/리스트 항목으로 이동(같은 레벨)
    - `C-c-u`: 상위 heading/리스트 항목으로 이동
- Markdown 단락 단위 이동: `M-{`, `M-}`, and `M-h`
    - `M-h`: 단락을 설정

### Preview with Marked 2 ###

제가 마크다운 파일을 미리보기 할 때면 항상 사용하는 Marked 2가 Emacs에서 편집 중인 파일도 쉽게 볼 수 있다는 사실을 [여기](https://jblevins.org/log/marked-2-command "Running Marked 2 from the Command Line")서 알게 되었습니다. 당연히 바로 적용해봤고, 잘 작동하는 것을 확인했습니다. 편집 중인 마크다운 문서를 미리보기 하려면 `C-c-c o`를 누르면 Marked 2가 실행됩니다. 필요에 따라 아래의 스크린샷처럼 Emacs와 Marked 2를 나란히 놓고 사용하면 Emacs에서 파일을 수정한 후 `C-x-s`로 저장하면 바로 옆의 화면에서 편집한 내용을 확인할 수 있습니다.[^1]

![screenshot of Emacs with marked 2](https://cl.ly/1y3V1Y3P3C2S/Image%202018-01-18%20at%204.17.54%20PM.png "Screenshot of Emacs with Marked2")

## 맺음말 ##

어색한 Emacs지만 그래도 또 제가 편하게 사용할 수 있도록 하나하나 맞춰가는 재미가 있습니다. 폰트도 위의 스크린샷과 달리 "이롭게 바탕체"로 바꾸니 더욱 글을 쓸 맛이 나네요. 저는 코딩을 하는 일이 거의 없으니 그냥 제가 쓴 글이 예쁘게 보이는 폰트로 설정했습니다. 앞으로 Emacs를 쓰면서 또 재밌는 것들을 포스팅하도록 하겠습니다. :)

[^1]: 평소에는 그냥 모두 적고 나서 편집할 때 가끔 이렇게 확인합니다. Marked 2는 링크가 적절하게 들어갔는지 등을 확인할 수 있어서 더욱 좋아합니다.
