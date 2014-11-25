---
layout: post
title: 나의 Pinboard 사용법
date: 2014-10-27 15:41:38
tags: pinboard webservice bookmarking
---


나는 [Pinboard][8451-002]를 접한 이후로 그 단순함과 빠릿빠릿함에 빠져서 지금은 RSS로 구독하는 사이트 외에 웹서핑을 통해 알게 되어 다시 볼 만한 사이트는 모두 Pinboard에 추가한다. RSS로 구독하고 있는 사이트에서도 다시 보고 싶은 글은 Pinboard에 저장하고 있다. 이글은 지금까지 내가 Pinboard를 이용하는 행태의 총정리이다.


1. Pinboard 소개
2. Pinboard 즐겨찾기 추가
	1. Safari 북마클릿으로 추가
	2. IFTTT를 이용한 즐겨찾기 추가
	3. Shiori를 이용한 즐겨찾기 추가
3. Pinboard 검색 및 보기
	3. LaunchBar와 Pinboard
	3. Shiori를 이용한 나의 Pinboard 브라우징
	3. Alfred 사용자를 위한 워크플로우
4. iOS에서 Pinboard 사용하기
5. 맺음말

## Pinboard 소개

핀보드는 온라인에서 찾은 링크를 보관할 수 있는 유료 웹서비스다. 유료 모델이 상당히 독특한데, 처음 가입할 때 가입비가 들고 그 이후에는 평생 무료다.[^1] 현재 $10.52[^2]에 가입할 수 있다. 모든 링크를 보관할 수 있으며 각 링크마다 공개할 것인지 비공개로 보관하여 나만 볼 수 있도록 할 것인지 선택할 수 있다. 광고가 없는 매우 간결한 디자인으로 보이는 것보다는 성능이 중요하다고 생각하는 사람이라면 매우 좋아할 것이다.

핀보드가 말하는 핀보드를 사용해야 하는 13가지 이유는 다음과 같다.

1. 핀보드는 매우 빠르다. 링크와 태그가 수만개에 달해도 빠르다.
2. [Delicious][3899-001], [Instapaper][3899-002], [Pocket][3899-003]를 포함한 여러 다른 사이트에서 즐겨찾기를 동기화할 수 있다.
3. 트위터 계정을 3개까지 연결하여 사용자의 트윗을 검색가능하도록 보관할 수 있다.
4. 신뢰할 수 있을만한 안정성을 제공한다. 서비스가 정지되는 경우는 좀처럼 없으며 있다 하더라도 잠시 후 정상화된다.[^3]
5. Pinboard는 간결하고 가벼운 디자인을 제공한다.
6. 가격 정책이 간단하고 비싸지 않다. 단 한 번의 가입비만 내면 된다.
7. 핀보드 사이트의 모든 것은 RSS 피드로 사용할 수 있다.
8. 다양한 형태로 데이터를 가져오고(Import) 내보낼(Export) 수 있다.
9. 손쉽게 사용할 수 있는 브라우저 플러그인을 제공한다.
10. 사용자의 비밀을 유지한다. 핀보드 사용자의 절반은 자신의 링크를 공개하지 않는다.
11. full API를 제공하며 많은 수의 써드파티 클라이언트 앱이 있다.
12. 이메일과 트위터를 통해 빠른 고객지원을 제공한다.
13. 납득할 정도의 적당한 비즈니스 모델을 갖고 있다.

자세한 설명은 핀보드에서 제공하는 [소개 페이지](https://pinboard.in/tour/ "Pinboard Site Tour — Better Online Bookmarking!")를 참고하기 바란다.

## Pinboard 즐겨찾기 추가

### Safari 북마클릿으로 추가

주로 맥북으로 웹서핑을 하는 나는 Safari 북마클릿을 이용해서 Pinboard에 보고 있는 페이지를 추가했다. 이것도 그리 나쁘진 않다. Safari에서 보고 있는 웹페이지를 Pinboard에 추가하고 싶으면 나의 경우 "⌘+3"을 누르면 바로 Pinboard에 추가할 수 있는 팝업 창이 생성되고, URL과 title은 현재 페이지의 정보가 저절로 입력된다. 추가로 description, tags를 입력하거나, private 즐겨찾기로 저장할 것인지, 나중에 읽기(read later)로 저장할 것인지 선택할 수 있다. 여기서 현재 추가하려는 페이지에 어울릴만한 태그를 제안(suggest)하니, 즐겨찾기를 추가하는 데 필요한 기능은 모두 있다. Pinboard에서 제공하는 [즐겨찾기를 저장하는 방법](https://pinboard.in/howto/#saving "Pinboard: howto page")에 더 자세한 설명이 있다.

### IFTTT를 이용한 즐겨찾기 추가

또 하나의 중요한 즐겨찾기를 추가하는 방법은 [IFTTT][8451-001]를 이용하는 것이다. IFTTT는 [트위터](http://twitter.com/)와 [ADN](http://app.net/)을 포함한 수많은 채널이 존재하고 각 채널 간의 상호작용을 자동화할 수 있는 서비스이다. 매우 편리한 서비스인데 무료이니 혹시 아직 사용해보지 않았다면 둘러보길 바란다. 내가 여기서 말하고자 하는 레시피는 트위터와 ADN에서 Favorite 한 트윗/포스트의 링크를 Pinboard에 공개 즐겨찾기(Public bookmark)로 저장하는 것이다. 매우 단순하고 직관적으로 레시피를 만들고 활성화할 수 있다.

 트위터와 ADN의 타임라인을 보다 보면 읽어보고 싶은 링크를 발견하는 경우가 많은데 나는 그때마다 링크를 클릭해서 링크 글을 읽지 않고 일단 Favorite 기능을 이용하여 "별표"한다. 이렇게 하면 위에서 활성화한 IFTTT 레시피를 통해 별표된 트윗/포스트가 내 Pinboard 즐겨찾기에 저장되고 나중에 원하는 시간에 읽을 수 있다. IFTTT는 실시간으로 동기화되는 것은 아니고 일정 시간 간격으로 트리거 되지만 내가 아주 많은 링크를 별표 하는 것은 아니라서 지금까지 문제가 된 적은 없다.

### Shiori를 이용한 즐겨찾기 추가

[Shiori](http://aki-null.net/shiori/ "Shiori - Pinboard and Delicious OS X client")는 [Pinboard][8451-002]와 [Delicious][8451-003]의 즐겨찾기를 검색하고 추가할 수 있는 OS X 클라이언트 앱이다. 단순하고 보기 좋은 인터페이스로 자신의 Pinboard에 즐겨찾기를 추가할 수 있으며 Safari, 크롬, 파이어폭스를 지원하여 웹브라우저에서 현재 보고 있는 페이지를 손쉽게 추가할 수 있다. 이때 현재 보고 있는 페이지의 URL과 제목이 저절로 들어가는 것은 물론이고 태그 입력 시 자동 완성 기능, Notes에 원하는 메모를 입력하거나, Private 즐겨찾기로 추가하는 옵션이 있다. 태그 입력하는 필드 오른편에 있는 "+"버튼을 누르면 태그 추천 창이 팝업된다. 설정에서 Private URLs 탭을 이용하면 특정 도메인의 페이지를 즐겨찾기 추가할 때 자동으로 Private 즐겨찾기로 등록하도록 설정할 수 있다.

 OS X 10.7 이상의 운영체제를 사용하고 있다면 [이곳](http://aki-null.net/shiori/release/Shiori_1.0.2.zip)에서 무료로 내려받을 수 있다. 나는 현재 요세미티에서 아무런 문제 없이 사용하고 있다. Shiori에 대한 다른 리뷰는 [MacStories](http://www.macstories.net/mac/shiori-free-pinboard-client-for-mac/ "Shiori, Free Pinboard Client for Mac – MacStories")와 [iDownloadBlog](http://www.idownloadblog.com/2013/11/30/shiori-my-favorite-pinboard-utility-for-the-mac/ "Shiori: my favorite Pinboard utility for the Mac")에서 볼 수 있다.

## Pinboard 검색 및 보기

Pinboard에 등록한 즐겨찾기를 검색하고 보는 방법은 크게 세 가지 방법으로 사용중이다. 가장 평범한 방법인 Safari에서 바로 <https://pinboard.in>에 접속해서 보는 방법과, LaunchBar 액션을 이용해서 보는 방법, Shiori를 이용하는 방법이다. <https://pinboard.in>에 접속해서 보는 방법은 따로 설명할 필요가 없을 것 같으니 나머지 두 가지 방법만 설명하겠다.

### LaunchBar와 Pinboard

나는 Pinboard와 관련된 LaunchBar 액션을 2개 쓰고 있다. 하나는 [나의 Pinboard 즐겨찾기를 보기 위한 액션](https://github.com/gillibrand/launchbar-pinboard "gillibrand/launchbar-pinboard")이다. 이것을 이용하면 내가 등록한 즐겨찾기를 태그 검색, 최근 25개의 항목, 읽지 않은 즐겨찾기 등의 다양한 옵션으로 접근할 수 있다. 이 액션이 내가 지금까지 찾은 LaunchBar 액션 중에서 가장 빠르게 최근 등록된 즐겨찾기를 보여주었다. [Macdrifter에 있는 글](http://www.macdrifter.com/2014/07/pinboard-actions-for-launchbar.html "Pinboard Actions for Launchbar")을 참고하면 액션을 실행했을 때 어떻게 보이는지 확인할 수 있다. 

 위의 액션은 Pinboard에 내가 등록한 즐겨찾기만 검색할 수 있다. 그래서 나는 다른 Pinboard 사용자들이 등록한 공개 즐겨찾기도 검색할 수 있는 [Pinboard Browse 액션](https://github.com/nbjahan/launchbar-pinboard/releases/tag/v1.0.2)을 하나 더 등록해서 쓰고 있다. Pinboard를 완벽하게 사용할 수 있는 액션 세트라서 자신의 Pinboard 즐겨찾기를 탐색할 수 있는 Pinboard 액션도 함께 있는데, 내가 사용해 본 바로는 새로운 즐겨찾기가 등록되면 최근 등록된 즐겨찾기 목록에 올라오는 데 시간 딜레이가 좀 있었다. 그래서 나는 이 액션 묶음 중에서 Pinboard Browse라는 액션만 활성화하여 사용하는 중이다.

### Shiori를 이용한 나의 Pinboard 브라우징

Shiori에서 대해서는 앞에 즐겨찾기를 추가하는 방법에서 소개했다. Shiori에서는 내가 등록한 Pinboard를 검색할 수 있다. 이미 등록한 즐겨찾기를 편집할 수는 없다. Shiori를 통해 등록한 북마크를 검색하면 축약어(abbreviations)를 사용하여 검색할 수 있어서 − 예를 들어 *Pinboard*를 *pbd*만 입력하여 검색할 수 있다 − 더욱 빠르게 검색할 수 있다는 장점이 있다. Shiori는 사용자의 습관을 학습하여 더 많이 Shiori를 사용할수록 더 똑똑해진다고 한다.

### Alfred 사용자를 위한 워크플로우
 
  Alfred 사용자를 위한 보너스가 있다. [jmjeong님이 공유한 워크플로우](http://www.alfredforum.com/topic/4426-alfred-pinboard-version-225-updated/ "alfred-pinboard version 2.25 (updated) - Share your Workflows - Alfred App Community Forum")를 확인해보길 바란다.
  
## iOS에서 Pinboard 사용하기

iOS에는 Pinboard를 편하게 사용할 수 있도록 돕는 어플이 많이 있다. 가장 대표적인 것들에는 [Pinswift](https://itunes.apple.com/kr/app/pinswift-fast-powerful-pinboard/id766741240?mt=8&uo=4), [Pushpin](https://itunes.apple.com/kr/app/pushpin-for-pinboard/id548052590?mt=8&uo=4), [Pinner][8451-004] 등이 있다. 나는 현재 Pinswift를 사용한다. Pinswift는 iOS 8에 대응하여 업데이트 되면서 많은 장점이 생겼다. 그 특징은 다음과 같다.

* **iOS 8 공유 익스텐션 지원**으로 시스템의 기본 공유 메뉴를 지원하는 곳이라면 어디서나 페이지를 즐겨찾기로 추가할 수 있다.
* **즐겨찾기 제목과 Description을 제안**하여 대부분의 웹페이지를 즐겨찾기에 추가할 때 제목과 설명을 따로 입력하지 않아도 된다. 물론 사용자가 원한다면 즐겨찾기 제목과 설명을 원하는대로 입력할 수 있다.
* **짧은 제목 제안**기능은 위의 즐겨찾기 제목 제안 기능에 추가되는 기능이라고 생각하면 되겠다. 페이지를 즐겨찾기에 추가할 때 사이트 이름이나 도메인 이름 등을 제거하여 더 짧은 제목을 제안한다.
* **태그 제안**과 **태그 자동완성 기능**은 기본이다.
* 클립보드에 URL 주소가 복사되어 있는 상태에서 Pinswift를 실행하면 클립보드에 있는 주소를 즐겨찾기에 추가할 것인지 물어본다.
* Pinswift 내에서 브라우징 하는 것도 상당히 매끄럽게 잘 실행된다.
* 사진, 움직이는 GIF, PDF 등 HTML URL이 아닌 것들은 *Open in* 액션을 이용하여 다른 앱에서 열 수 있다.
* 트위터 링크나 사용자 이름은 사용자가 선택한 트위터 앱에서 열리도록 설정할 수 있다. 나는 Tweetbot 3를 사용하기에 Tweetbot 3에서 열리도록 설정해뒀다.
* URL scheme를 지원하여 [Drafts 4][8451-005], [Launch Center Pro][8451-006], [DayOne][8451-007], [Due][8451-008] 등의 다른 앱들과 연계가 잘 된다.

나는 Pinswift를 사용하기에 Pinswift의 특징을 간략하게 설명했지만 꼭 Pinswift가 아니어도 Pinboard를 매우 편하게 사용할 수 있도록 하는 앱들이 많으니 아이폰이나 아이패드를 사용하는 사람은 Pinboard 전용 앱을 써볼 것을 권장한다.

## 맺음말

지금까지 내가 Pinboard를 사용하는 방법을 정리했다. 긴 글을 적으면서 내가 Pinboard를 접한 이후로 벌써 이런 시도들을 해봤구나 하는 생각이 들기도 하고 Pinboard를 가장 잘 사용하기 위해 나보다 훨씬 다양한 방법을 시도해 본 사람도 분명 있을 것이란 생각도 들었다. 이 글이 이제부터 Pinboard를 사용해보려는 생각을 갖고 있는 사람이나 이미 Pinboard를 사용하고는 있지만 [Pinboard 웹사이트](http://pinboard.in "Pinboard website")만 사용하다가 다른 방법을 찾아 헤메는 사람에게 도움이 되었으면 좋겠다.

[8451-001]: https://ifttt.com/
[8451-002]: https://pinboard.in/
[8451-003]: https://delicious.com/
[8451-004]: https://itunes.apple.com/kr/app/pinner-for-pinboard/id591613202?l=en&mt=8
[8451-005]: https://itunes.apple.com/kr/app/drafts-4-quickly-capture-notes/id905337691?l=en&mt=8
[8451-006]: https://itunes.apple.com/kr/app/launch-center-pro/id532016360?l=en&mt=8
[8451-007]: https://itunes.apple.com/kr/app/day-one-journal-notes-diary/id421706526?l=en&mt=8
[8451-008]: https://itunes.apple.com/kr/app/due-super-fast-reminders-reusable/id390017969?l=en&mt=8
[3899-001]: https://delicious.com/
[3899-002]: https://www.instapaper.com/
[3899-003]: https://getpocket.com/

[^1]: 링크의 원래 페이지가 없어지더라도 볼 수 있도록 보관하는 "Bookmark Archive" 기능을 이용하려면 "$25/년"의 별도 플랜을 이용해야 한다.

[^2]: 가입자가 늘어날수록 가입비가 비싸진다. 내가 가입할 때도 $10 정도였으니 지금 가입자가 많이 늘어나고 있지는 않은 것 같다.

[^3]: 나는 지금까지 Pinboard가 작동하지 않는 것을 본 적이 없다.