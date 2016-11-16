---
layout: post
title: kramdown 기본 기로 목차 쉽게 넣기
date: 2016-11-16 17:10:40
tags: jekyll toc kramdown github
---
[한량넷](halryang.net)은 [Jekyll](https://jekyllrb.com/) + [GitHub pages](https://pages.github.com/)를 이용합니다. 긴 글을 작성해서 올리는 경우 목차가 있으면 글의 내용이 한 눈에 들어와서 좋습니다. 그래서 이전에 [마크다운 문서의 목차 생성기](http://halryang.net/markdown-toc-generator/ "Markdown TOC Generator - 한량넷")를 포스팅하고 지금까지 써왔습니다. 이전 글의 생성기를 이용하면 목차의 각 항목 앞에 들어가는 기호/숫자 등을 마음대로 정할 수 있다는 장점이 있습니다. 하지만 목차를 보여주기만 하고 목차의 항목을 클릭해서 해당 내용으로 이동하는 기능이 없다는 것이 조금 아쉬웠습니다. 그러던 중 kramdown 이 기본으로 목차를 넣는 기능을 제공한다는 것을 알게 되어 소개합니다.

[kramdown](http://kramdown.gettalong.org/index.html)은 Jekyll에서 마크다운을 처리하는데 사용하는 기본 처리엔진입니다. kramdown이 마크다운을 HTML로 전환할 때 헤더 ID를 자동으로 생성한다고 합니다. 이 헤더 ID를 이용해서 kramdown을 이용하는 Jekyll 블로그 글에는 원하는 곳에 아래처럼 코드 두 줄을 넣으면 간단하게 목차를 넣을 수 있습니다.[^1]

```
1. 목차
{:toc}
```

[^1]: 이 방식으로 목차를 만들어 넣은 포스트가 궁금하시면 [이 글](http://halryang.net/How-I-Use-TaskPaper/#alfred-workflow-for-taskpaper "나의 TaskPaper 사용법 - 한량넷")을 보세요.
