---
layout: post
title: Jekyll에서 Youtube 영상을 Responsive하게 임베딩하기
date: 2014-11-18 11:04:40
summary: youtube_tag 플러그인을 사용해서 Responsive하게 YouTube 영상을 Jekyll에 보기 좋게 임베딩하자.
tags: embed youtube responsive jekyll plugin
---
Jekyll은 정적인 사이트를 만드는 툴로서, 지금까지 제가 본 바론 글을 쓰기에 최적화 되어 있습니다. Code highlight도 있어 개발자가 쓰기에 딱 좋아보입니다. 하지만 저는 개발은 전혀 모르고 개인 블로그를 가볍게 운영하려고 Jekyll을 사용하고 있습니다. 가끔 Youtube에서 좋은 영상을 발견하면 블로그에 올려두기도 하는데, Jekyll에선 Liquid Tag를 이용해서 Youtube 영상을 공유할 수 있습니다.

저는 Liquid Tag는 [ttscoff][5141-0001]가 만든 플러그인([GitHub Repo](https://github.com/ttscoff/JekyllPlugins/tree/master/YouTube "JekyllPlugins/YouTube at master · ttscoff/JekyllPlugins · GitHub"))을 사용합니다. Youtube 외에 Vimeo 등을 임베딩하는 [OEmbed](https://gist.github.com/vanto/1455726 "OEmbed Liquid Tag for Jekyll")도 쓰려고 시도해봤으나 뭐가 문제인지 영상이 나오지 않았습니다.

YouTube Jekyll Plugin은 로컬 지킬에 "_plugins" 폴더를 만들고 "youtube_tag.rb" 파일을 넣으면 사용 준비가 끝난 것입니다. 이제 글을 적다가 영상을 넣기 원하는 곳에 `{ % youtube https://www.youtube.com/watch?v=G33WiEktUo8 % }`의 형식으로 YouTube 주소를 넣으면 됩니다. 글만 있으니 말이 나온 김에 좋은 노래 하나 삽입하고 계속 글을 이어가죠.

<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='http://www.youtube.com/embed/4Pax5vCQbMA' frameborder='0' allowfullscreen></iframe></div>

ttscoff의 플러그인은 반응형으로 삽입됩니다. 크기가 작은 모바일 기기에서도 영상이 잘리지 않는다는 장점이 있지요. 한 가지 마음에 들지 않는 점이 있다면 영상 위 아래로 검은 여백이 생긴다는 것이었습니다. 그래서 방법을 열심히 검색해서 <<http://embedresponsively.com/>>라는 사이트를 알게 되었습니다. youtube 영상 주소를 입력하면 반응형으로 임베딩할 수 있는 주소를 알려주는 곳입니다. 예를 들면 아래와 같은 형태로 나옵니다.

```html
<style>.embed-container { position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto; } .embed-container iframe, .embed-container object, .embed-container embed { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }</style><div class='embed-container'><iframe src='http://www.youtube.com/embed/eqSCunKweu8' frameborder='0' allowfullscreen></iframe></div>
```

물론 이 주소를 마크다운 문서에 그대로 붙여 넣고 사용해도 되지만 문서를 편집하면서 보기에 영 좋지 않습니다. 그래서 "youtube_tag.rb" 파일을 위 사이트에서 만들어진 주소를 참고해서 좀 변형했습니다. 그랬더니 위아래에 있던 검은 여백이 사라졌습니다. 이것으로 제가 원하는 모습의 youtube 임베딩이 가능해졌습니다. 제가 수정한 파일은 [이곳](/assets/youtube_tag.rb)을 누르시면 내려받을 수 있습니다.

[5141-0001]: https://twitter.com/ttscoff