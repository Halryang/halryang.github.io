---
layout: post
title: Bigfoot을 사용하여 지킬의 각주를 보기 좋게 만들자
date: 2014-12-08 11:25:33
tags: Bigfoot footnote jekyll
---
[윤지만님의 글](http://yoonjiman.net/2014/12/07/bigfoot/ "블로그의 각주를 멋지게 만들어 주는 Bigfoot - Yoon Jiman")을  읽고 Bigfoot이라는 jQuery 플러그인을 알게 되었다. 전에 [외부 링크는 새로운 탭에서 열리도록 설정](http://halryang.github.io/Open-external-link-in-new-tab/ "jquery를 이용해서 외부 링크를 새 탭에서 열기 :: 한량의 Jekyll 블로그")하는 것도 jQuery를 사용하는 것이었기에 Bigfoot도 지킬에 적용할 수 있겠다는 생각이 들어서 여기에도 적용해 보았다.

각주를 클릭하려면 작은 숫자를 힘겹게 터치 혹은 클릭해야 하고, 클릭하면 문서의 가장 아랫부분으로 이동하여 각주 내용을 읽고 다시 본문에서 읽던 부분으로 돌아가서 글을 읽어야 한다. 정말 중요한 내용의 각주도 아니고 주로 사담을 덧붙이는 용도로 각주를 이용하고 있는 나는 글을 읽는 사람에게 미안할 정도다.

[Bigfoot](http://www.bigfootjs.com/ "bigfoot.js")은 각주를 클릭하기 쉬운 크기의 버튼 형태로 만들어 준다. 각주를 클릭하면 팝오버[^1] 창을 띄워 문서의 아래로 내려가지 않고서도 각주 내용을 확인할 수 있다. 팝오버 창 밖의 본문을 클릭하면 다시 읽던 본문을 편하게 이어서 읽을 수 있다.

워드프레스에는 편하게 설정할 수 있는 플러그인이 있는 모양인데, 나는 지킬을 쓰고 있기에 직접 작업해야 한다. 가장 큰 도움을 받은 글은 [Bigfoot footnotes in Jekyll](http://sherifsoliman.com/2014/11/07/Bigfoot%20in%20Jekyll/ "Bigfoot footnotes in Jekyll")이었다.

일단 [이곳](http://jquery.com/download/)에서 jQuery를 내려받고, 지킬 에서 이전부터 js 파일을 담던 폴더에 넣었다. 그리고 Bigfoot 파일은 윤지만 님께서 공유하신 [깃허브 Repo](https://gist.github.com/ilazakis/550767c780cc5a6d625e)에서 내려받아 bigfoot.min.js는 js 폴더에, bigfoot-default.css의 내용을 내 지킬의 style.scss에 붙여 넣었다.[^2]

나는 `head.html`이 따로 없으므로 `_layouts/default.html`의 `<head>`에 바로 아래의 코드를 삽입했다.

```html
<script type="text/javascript" src="/js/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="/js/bigfoot.min.js"></script>
<script type="text/javascript">
        var bigfoot = $.bigfoot(
                       {
                       actionOriginalFN: "ignore",
                       positionContent: "true"
                       }
        );
</script>
```

이렇게 설정하고 나니 지금과 같이 Bigfoot을 적용할 수 있었다. 이제 본문 중 각주를 넣기 원하는 곳에 `[^1]`을 적고, `[^1]: 팝오버 창은 이렇게 작동한다. 누르기 편하고 마음에 든다. :)` 와 같이 각주의 내용을 채우면 된다.

한 가지 아쉬운 점은 Bigfoot을 적용하고 보니 각주 내용에서 본문의 해당 부분으로 돌아가는 기능이 작동하지 않는다. 이 점만 고쳐지면 정말 흡족할 것 같다. 아랫 부분에서 본문의 해당 위치로 돌아가는 기능이 작동하지 않아서 지금은 아예 본문 아래에 각주 내용은 숨겨두었다. 이게 보기엔 더 깔끔하다.

***

### 2014-12-09 **변경사항**

오늘 [Bigfoot](http://www.bigfootjs.com/ "bigfoot.js")에서 다시 `bigfoot.min.js`와 `bigfoot-number.css`파일을 내려받아서 덮어 씌우고 `default.html`파일에 옵션 값으로 `anchorPattern: /(fn|footnote|note)[\-_\d]/gi`를 추가했다. Bigfoot의 각주에서 기본 anchor pattern이 `/#fnref:1`의 형태인데, 내가 쓰는 Redcarpet는 `/#fnref1`의 형태라서 이걸 맞춰주었다. 이게 문제점이었는지는 모른다. 하지만 고치고 나서 각주에서 본문으로 이동이 가능하다. :)

[^1]: 팝오버 창은 이렇게 작동한다. 누르기 편하고 마음에 든다. :)

[^2]: 나는 _scss 폴더에 넣어서 import 하는 방식이 잘 적용되지 않아서 이렇게 했다. 어쨌든 제대로 작동한다.