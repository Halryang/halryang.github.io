---
layout: post
title: 나눔고딕 구글 웹폰트 로더 적용하기
date: 2016-12-01 10:51:59
tags: webfont
---
이전엔 구글 웹폰트를 이용해서 나눔 고딕을 적용하는 방법으로 CSS에 `@import`를 사용했다. 블로그에 접속 속도가 느려지는 것 같아서 다시 구글 폰트를 사용하지 않을까 했는데, 윈도우즈 피씨에서 접속할 때 폰트가 영 보기 좋지 않아서 다른 방법을 찾았다. [이곳](http://www.letmecompile.com/%EB%82%98%EB%88%94%EA%B3%A0%EB%94%95-%EA%B5%AC%EA%B8%80-%EC%9B%B9%ED%8F%B0%ED%8A%B8webfont-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0/) "나눔고딕 구글 웹폰트(Webfont) 사용하기 | Knowledge Logger") 을 참고하여 CSS import 전에 웹폰트 로드하는 법을 적용했더니 좀 나아졌다. 아직 나눔고딕폰트가 정식 구글 웹폰트가 아닌 ealry access형태로 제공되고 있기 때문에 아래처럼 url까지 적어줘야 제대로 작동한다.

```
<script src="//ajax.googleapis.com/ajax/libs/webfont/1.4.10/webfont.js"></script>
<script type="text/javascript">
  WebFont.load({
 
    // For early access or custom font
    custom: {
        families: ['Nanum Gothic'],
        urls: ['http://fonts.googleapis.com/earlyaccess/nanumgothic.css']
    }
 
  });
</script>
```

실제 폰트 적용은 다음과 같이 한다.

```
body {
	font-family: “Nanum Gothic”, sans-serif;
}
```

