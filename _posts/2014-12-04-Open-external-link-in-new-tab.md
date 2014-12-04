---
layout: post
title: jquery를 이용해서 외부 링크를 새 탭에서 열기
date: 2014-12-04 14:19:55
tags: jekyll js
---
오늘은 그동안 생각지 못했던 부분인 외부 링크를 새 탭에서 여는 것을 적용했다. 블로그에 글을 올릴 때 외부 링크를 거는 경우가 많다. 바로 어제 적은 [Typed 리뷰 글](http://halryang.github.io/Typed-review/ "Typed - 마크다운 문서 편집 앱 짧은 사용기 :: 한량의 Jekyll 블로그")만 봐도 짧은 글에 10개의 링크가 들어 있다. 그런데 이 링크들을 눌러서 보고 다시 내 블로그 글로 돌아오려면 그 과정이 상당히 귀찮다. 그래서 외부 링크는 새 탭에서 열리도록 설정했다.

[Aly Badawy의 글](https://alybadawy.com/post/open-external-links-in-new-tab-using-jquery "Aly Badawy - Open external links in new tab using jquery")을 보고 그대로 따라했다. [깃허브 레포](https://github.com/AlyBadawy/external_links)에 있는 `com.alybadawy.external_links.js` 파일을 적용할 지킬의 js 폴더에 넣고 default, post, page 레이아웃에 아래 코드를 삽입하면 된다.

```javascript
<script type="text/javascript" src="http://code.jquery.com/jquery-1.10.2.min.js"></script>
<script type="text/javascript" src="js/com.alybadawy.external_links.js"></script>
```