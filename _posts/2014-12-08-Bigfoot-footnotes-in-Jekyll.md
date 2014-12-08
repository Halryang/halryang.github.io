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

`style.scss`에 삽입한 코드는 아래와 같다.

```css
// Bigfoot css
.footnote-button { position: relative; z-index: 5; top: -0.15em; box-sizing: border-box; display: inline-block; padding: 0.34em; margin: 0 0.1em 0 0.2em; border: none; border-radius: 0.3em; cursor: pointer; opacity: 0.3; background-color: #464646; line-height: 0; vertical-align: middle; text-decoration: none; -webkit-transition-property: opacity; -moz-transition-property: opacity; -ms-transition-property: opacity; transition-property: opacity; -webkit-transition-duration: 0.25s; -moz-transition-duration: 0.25s; -ms-transition-duration: 0.25s; transition-duration: 0.25s; }
.footnote-button:hover { opacity: 0.6; }
.footnote-button:active { opacity: 0.6; }
.footnote-button.active { opacity: 0.9; -webkit-transition-delay: 0.15s; -moz-transition-delay: 0.15s; -ms-transition-delay: 0.15s; transition-delay: 0.15s; }

.footnote-circle { display: inline-block; width: 0.32em; height: 0.32em; margin-right: 0.224em; border-radius: 100%; background-color: #e6e6e6; border: none; line-height: 0.5em; }
.footnote-circle:last-child { margin-right: 0; }

.footnote-content { position: fixed; z-index: 10; bottom: auto; left: auto; box-sizing: border-box; max-width: 90%; margin: 1.21924em auto; display: inline-block; -webkit-transform: scale(0.1) translateZ(0); -moz-transform: scale(0.1) translateZ(0); -ms-transform: scale(0.1) translateZ(0); transform: scale(0.1) translateZ(0); -webkit-transform-origin: 50% 0; -moz-transform-origin: 50% 0; -ms-transform-origin: 50% 0; transform-origin: 50% 0; background: #fafafa; opacity: 0; border-radius: 0.5em; border: 1px solid #c3c3c3; box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.3); -webkit-transition-property: opacity, -webkit-transform; -moz-transition-property: opacity, -moz-transform; -ms-transition-property: opacity, -ms-transform; transition-property: opacity, transform; -webkit-transition-duration: 0.25s; -moz-transition-duration: 0.25s; -ms-transition-duration: 0.25s; transition-duration: 0.25s; }
.footnote-content.active { -webkit-transform: scale(1) translateZ(0); -moz-transform: scale(1) translateZ(0); -ms-transform: scale(1) translateZ(0); transform: scale(1) translateZ(0); opacity: 0.97; }
.footnote-content.bottom { -webkit-transform-origin: top; -moz-transform-origin: top; -ms-transform-origin: top; transform-origin: top; }
.footnote-content.top { -webkit-transform-origin: bottom; -moz-transform-origin: bottom; -ms-transform-origin: bottom; transform-origin: bottom; }
.footnote-content.scrollable:after { content: '...'; position: fixed; bottom: 0.45em; right: 50%; z-index: 20; width: 1.5em; margin-right: -0.75em; opacity: 1; background-color: #fafafa; font-family: Georgia; font-weight: bold; font-size: 1.8em; text-align: center; color: rgba(0, 0, 0, 0.08); line-height: 0; -webkit-transition-property: opacity; -moz-transition-property: opacity; -ms-transition-property: opacity; transition-property: opacity; -webkit-transition-duration: 0.25s; -moz-transition-duration: 0.25s; -ms-transition-duration: 0.25s; transition-duration: 0.25s; -webkit-transition-delay: 0.4s; -moz-transition-delay: 0.4s; -ms-transition-delay: 0.4s; transition-delay: 0.4s; }
.footnote-content.scrollable.fully-scrolled:after { opacity: 0; -webkit-transition-delay: 0s; -moz-transition-delay: 0s; -ms-transition-delay: 0s; transition-delay: 0s; }
.footnote-content.scrollable .footnote-main-wrapper:before, .footnote-content.scrollable .footnote-main-wrapper:after { content: ' '; position: absolute; width: 100%; z-index: 12; }
.footnote-content.scrollable .footnote-main-wrapper:before { top: -1px; left: 0; height: 1.1em; border-radius: 0.5em 0.5em 0 0; background: #fafafa; background: -moz-linear-gradient(top, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: -webkit-gradient(linear, left top, left bottom, color-stop(0%, #fafafa), color-stop(50%, #fafafa), color-stop(100%, rgba(250, 250, 250, 0))); background: -webkit-linear-gradient(top, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: -o-linear-gradient(top, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: -ms-linear-gradient(top, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: linear-gradient(to bottom, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); }
.footnote-content.scrollable .footnote-main-wrapper:after { bottom: -1px; left: 0; height: 1.2em; border-radius: 0 0 0.5em 0.5em; background: #fafafa; background: -moz-linear-gradient(bottom, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: -webkit-gradient(linear, left bottom, left top, color-stop(0%, #fafafa), color-stop(50%, #fafafa), color-stop(100%, rgba(250, 250, 250, 0))); background: -webkit-linear-gradient(bottom, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: -o-linear-gradient(bottom, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: -ms-linear-gradient(bottom, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); background: linear-gradient(to top, #fafafa 0%, #fafafa 50%, rgba(250, 250, 250, 0) 100%); }
.footnote-content ::-webkit-scrollbar { display: none; }

.footnote-main-wrapper { position: relative; z-index: 14; box-sizing: border-box; overflow: hidden; margin: 0; max-width: 22em; background-color: #fafafa; border-radius: 0.5em; -webkit-transition-property: max-height; -moz-transition-property: max-height; -ms-transition-property: max-height; transition-property: max-height; -webkit-transition-duration: 0.25s; -moz-transition-duration: 0.25s; -ms-transition-duration: 0.25s; transition-duration: 0.25s; }

.footnote-content-wrapper { position: relative; z-index: 8; max-height: 15em; padding: 1.1em 1.3em 1.2em; box-sizing: border-box; overflow: auto; -webkit-overflow-scrolling: touch; background: #fafafa; border-radius: 0.5em; }
.footnote-content-wrapper img { max-width: 100%; }
.footnote-content-wrapper *:last-child { margin-bottom: 0; }
.footnote-content-wrapper *:first-child { margin-top: 0; }

.tooltip { position: absolute; z-index: 12; box-sizing: border-box; margin-left: -0.65em; width: 1.3em; height: 1.3em; -webkit-transform: rotate(45deg); -moz-transform: rotate(45deg); -ms-transform: rotate(45deg); transform: rotate(45deg); background: #fafafa; border: 1px solid #c3c3c3; box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.3); border-top-left-radius: 0; }

.bottom .tooltip { top: -0.65em; bottom: auto; }

.top .tooltip { bottom: -0.65em; top: auto; }


/* Lazakis */
.footnote-button span {
	color: white;
	font-family: "Ideal Sans SSm A, Helvetica Neue", Helvetica, Arial, sans-serif;
}

.footnote-button {
	border-radius: 1em;
	min-width: 32px;
	text-align: center;
	height: 1.3em;
	top: -0.25em;
	font-size: 0.75em;
	font-weight: 600;
	padding-top: 0.75em;
	-webkit-font-smoothing: antialiased;
}
```

이렇게 설정하고 나니 지금과 같이 Bigfoot을 적용할 수 있었다. 이제 본문 중 각주를 넣기 원하는 곳에 `[^1]`을 적고, `[^1]: 팝오버 창은 이렇게 작동한다. 누르기 편하고 마음에 든다. :)` 와 같이 각주의 내용을 채우면 된다.

한 가지 아쉬운 점은 Bigfoot을 적용하고 보니 각주 내용에서 본문의 해당 부분으로 돌아가는 기능이 작동하지 않는다. 이 점만 고쳐지면 정말 흡족할 것 같다. 아랫 부분에서 본문의 해당 위치로 돌아가는 기능이 작동하지 않아서 지금은 아예 본문 아래에 각주 내용은 숨겨두었다. 이게 보기엔 더 깔끔하다.

[^1]: 팝오버 창은 이렇게 작동한다. 누르기 편하고 마음에 든다. :)

[^2]: 나는 _scss 폴더에 넣어서 import 하는 방식이 잘 적용되지 않아서 이렇게 했다. 어쨌든 제대로 작동한다.