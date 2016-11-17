---
layout: post
title: 지킬 블로그에 검색창 달기
date: 2016-11-17 23:28:10
tags: jekyll blogging search js plugin
---
제가 지킬 블로그를 시작하면서 원하는 기능 중에 최근까지 구현하지 못한 것이 하나 있었습니다. 바로 검색창이었어요. 사이트 안에서 원하는 글을 빨리 찾을 수 있으면 좋겠는데, 태그만으로는 성에 차지 않았습니다. [telemachus][6812-0001]님의 [블로그](http://scriveners.github.io/)에 검색창이 있는 것을 확인하고 거의 그대로 가져왔습니다. 이제 [검색 페이지](http://www.halryang.net/search/)의 검색창에서 한량넷의 글을 검색할 수 있습니다.

검색 기능을 어떻게 구현했는지는 [여기](https://github.com/christian-fei/Simple-Jekyll-Search "christian-fei/Simple-Jekyll-Search: A JavaScript library to add search functionality to any Jekyll blog.")에서 확인하실 수 있습니다. 저는 잘 몰라요.

제가 한 것은 다음과 같습니다.

1. 지킬의 루트 폴더에 [search2.json](http://dr.halryang.net/yNbR), [Simple-Jekyll-Search.sublime-project](http://dr.halryang.net/m5YZ)를 넣기
2. 지킬의 루트 폴더 아래 `dest`라는 폴더를 만들고 [jekyll-search.js](http://dr.halryang.net/kboe), [jekyll-search.min.js](http://dr.halryang.net/AdWc) 넣기
3. 지킬의 루트 폴더 아래 `_plugins`라는 폴더를 만들고 [simple_search_filter.rb](http://dr.halryang.net/GYNE) 넣기
4. 지킬의 루트 폴더 아래 [search.html](http://dr.halryang.net/G2ZH) 파일 만들어 넣기
	* 위의 파일 내용에서 `<div id="results">` 부터 `</div>`까지의 내용은 이미 쓰고 있던 tag 검색을 위한 것으로 이 글에서 이야기하는 simple-jekyll-search와는 관계가 없는 코드입니다.
5. `images/icon/`폴더에 적당한 아이콘을 `search.png`로 저장하기
6. 지킬의 `_layout` 폴더 아래 `default.html` 파일의 적당한 곳에 `<a href="{{ site.baseurl }}/search/"><img src="{{ site.baseurl }}/images/icon/search.png" /></a>`로 링크 넣기

이제 한량넷에서 봤는데 어딨었더라 하는 글이 있다면 가장 상단 우측의 돋보기 아이콘을 누르고 편하게 검색하세요! :)


[6812-0001]: https://twitter.com/telemachus


<!-- Report:
(0:118:23): [](!@t telemachus) => https://twitter.com/telemachus
(): Processed: 2 links, 0 errors.
-->

