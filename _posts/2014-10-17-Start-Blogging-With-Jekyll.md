---
layout: post
title: GitHub pages를 이용하여 Jekyll Blog를 만들자
tags: jekyll github blogging
---
# Intro

GitHub pages를 이용하여 Jekyll Blog를 만들어 봤다. 기본적인 지식도 제대로 갖추지 못한 내가 CLI를 MS-DOS시절 이후 오랜만에 조금씩 써가면서 만드는데 도움이 된 글들을 먼저 링크하고 싶다.

- [지킬로 깃허브에 무료 블로그 만들기 - @n0lb00's Blog](http://nolboo.github.io/blog/2013/10/15/free-blog-with-github-jekyll/)
- [Jekyll From Scratch - Getting Started](http://pixelcog.com/blog/2013/jekyll-from-scratch-introduction/)
- [**Using Jekyll with Pages**](https://help.github.com/articles/using-jekyll-with-pages/)

가장 도움이 된 글은 역시 굵게 표시한 마지막 링크 글이다. GitHub help 페이지에서 Jekyll을 Pages와 어떻게 함께 사용할 수 있는지 잘 설명했다.

## 준비단계

블로그를 만들기 전 나의 환경은 다음과 같았다.

* Macbook Air 2012 13inch
* GitHub 미가입: 이전에 가입한 줄 알았는데 아니었다.
* X-code 미설치
* 프로그래밍에 대한 배경 지식 없음

### Jekyll을 설치하기 위한 요구사항

* Ruby (Development headers를 포함)
* RubyGems
* Linus, Unix, or Mac OS X
* NodeJS, or another JavaScript runtime (for CoffeeScript support)

사실 나는 이 항목들 각각이 무엇을 의미하는지도 모른다. 그러나 용감히 시도해보기로 했다.

### Xcode, Command-Line Tools 설치

Mac OS X에서 Jekyll을 설치하기 위해 가장 먼저 해야 하는 것은 Xcode와 Command-Line Tools를 설치하는 일이었다. Xcode는 App store에서 검색해서 쉽게 설치할 수 있었으나 'Preferences → Downloads → Components'에 들어가도 Command-Line Tools를 다운로드 하는 것이 보이지 않았다. 결국 따로 구글링해서 [Xcode Command Line Tools for Mac OS X 10.10 Yosemite · RailsApps](http://railsapps.github.io/xcode-command-line-tools.html) 페이지를 보고 CLI 명령어를 입력하여 설치할 수 있었다.

## Jekyll을 설치하자

Xcode와 Command-Line Tools를 설치하고 나니 이제 gem install jekyll이 정상 작동했다! 야호!!! 작동이 되고 나면 상당히 빠른 시간 안에 Jekyll 설치가 끝난다. 약간 허무하다. 이제 로컬 디렉토리(내 맥북 안 어딘가)에 지킬을 설치하고 온라인 GitHub에 블로그를 올릴 수 있게 설정하면 된다.

### 로컬 디렉토리 Jekyll 설치

이 문서 저 문서 보면서 하다보니 여기저기에서 약간씩 섞였다. 나는 로컬 디렉토리 이름은 blog로 로컬 디렉토리에 설치했다.

	jekyll new blog

이렇게 입력하면 된다. 엄청 간단하다. 이렇게 blog라는 디렉토리에 Jekyll을 설치했다. Jekyll 설치가 잘 되었는지 확인한다.

	cd blog
	jekyll serve -w

위의 명령어를 입력하고 Localhost:4000 이라고 사파리 주소창에 입력하면 로컬에 설치된 Jekyll이 어떻게 보이는지 확인할 수 있다.

### GitHub에 Repository 만들기

GitHub를 이용하면 무료로 Jekyll 블로그를 만들 수 있다는 글을 보고 만들기 시작한 것이므로 당연히 GitHub pages를 이용하기 위해 GitHub 계정을 만들었다. Repository는 내가 만든 파일들과 폴더들을 올려놓을 수 있는 공간인 듯하다. Repository를 흔히 Repo라고 줄여 말하는 것 같아 나도 경제적으로 아래에는 Repo라고 적겠다.

1. GitHub에 가입을 한다.
2. E-mail verification을 한다. (권고하는 사항이므로 바로 했다)
3. Repo 만들기를 누른다. (무료로 공개 Repo는 여러 개 생성 가능)
4. 나는 Repo 이름을 halryang.github.io 라고 정했다.

### 로컬 디렉토리를 GitHub repo에 올리기

	$ git init
	$ git add -A && git commit -m "initial commit"
	$ git remote add origin GitHubRepo주소

나는 이 과정이 가장 힘들었다. 처음엔 GitHub Repo 주소를 넣는 곳에 ".git"을 입력하지 않아서 push가 되지 않는 것을 왜 안 되지 하고 살펴보고 있었다. CLI는 오타를 용납하지 않으니 명령어를 넣을 때 잘 살펴서 입력해야 한다. 이런 문제를 수정하고서도 Jekyll을 설치한 로컬 디렉토리에서 Repo에 몇 번을 push해도 halryang.github.io에 들어가면 아무런 페이지가 뜨지 않았다.

 [Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages/)를 참고하여 Bundler를 설치하고 Gemfile을 만들어서 로컬 디렉토리에 넣은 후 bundle install을 하니 그제서야 halryang.github.io 에서 Jekyll을 확인할 수 있었다.
 
 gem install github-pages 를 통해서도 Jekyll을 설치할 수 있으나 문제가 발생할 수 있다고 적혀 있다(If you decided to skip step #2, you can still install Jekyll with the command gem install github-pages, but you may run into trouble down the line).
 
 gemfile과 Gemfile.lock이 생성되어 새로 push하는 방법을 몰라서 git add 명령어를 배우게 되었다. 겨우 Push만 했을 뿐 아직 익히진 못했다.
 
 ```
 git add . -A && git commit -m "커밋 내용"
 git push -u origin master
 ```

이렇게 두 줄의 터미널 명령어로 블로그의 변경사항을 커밋하고 푸쉬할 수 있다. 변경한 내용이 사이트에 적용되는 데에는 약간의 시간이 걸릴 수 있지만 거의 바로바로 적용된다. [지킬 포스팅의 자동화](http://halryang.net/automation-for-jekyll-posting/)라는 글에 적은 것처럼 나는 TextExpander snippet을 만들어서 조금 더 편하게 사용하고 있다.

## 이제 블로그를 커스터마이징하자

### Jekyll을 configure하는 방법

거창하게 커스터마이징이라고 적었지만 내가 지금까지 한 것은 겨우 블로그 이름(title), 간략한 설명(description), email 주소, 트위터 사용자명, GitHub 사용자명, markdown 세팅을 바꾼 것 뿐이다. 이 모든 설정은 _config.yml 파일에 들어 있으니 로컬 디렉토리에서 이것을 수정하여 저장하고 git add, git push하면 된다.

### 테마 적용, 스타일 변경

Jekyll 또한 많은 테마가 이미 나와있고 테마를 적용하고 나서도 개인 취향에 따라 css 변경 등을 통해 입맛에 맞는 사이트를 만들 수 있다. 나는 이제 시작하는 입장이므로 지금은 테마 적용, 스타일 변경, 플러그인 추가를 하지 않았다. 후에 테마를 적용하면 그것을 주제로 또 포스팅을 할 예정이다.

## 이제 글을 써보자

지금까지 Jekyll을 GitHub에 올리고 halryang.github.io 라는 주소를 통해서 들어가려고 많은 과정을 거쳤다. 이제 드디어 블로그에 글을 올릴 수 있다. 기본적인 개념은 내가 원하는 글을 마크다운으로 작성해서 로컬 디렉토리에 _post 폴더에 넣은 후 push 하면 GitHub에 파일이 올라가고 그 파일을 Jekyll이 보기 좋게 뿌려주는 것이다.

### 블로그 포스팅의 원칙

WISWIG(What I See What I Get) 방식으로 글을 발행하는 여타 많은 블로그와 달리 Jekyll은 각 블로그 글마다 파일이 따로 있다. Jekyll이 각각의 파일을 보여주는 것이다. 따라서 글을 발행하려면 글을 파일로 로컬 디렉토리에 저장해야 한다. 이때 블로그 포스트는 반드시 _post 안에 넣어야 한다. Jekyll은 이 폴더에 있는 파일만 블로그 포스트로 인식한다. 그리고 블로그 포스트 파일명은 항상 *YYYY-MM-DD-post-name.확장자*(나는 마크다운으로 작성하고 보통 **md**확장자를 사용한다) 형식으로 지정되어야 한다.

블로그 포스트는 항상 파일의 제일 앞에 front matter를 적어야 한다. Jekyll은 front matter 블록으로 시작되는 파일만 처리한다. 각 블로그 포스트의 front matter에는 "title"과 "layout" 필드는 반드시 들어가야 한다. date는 파일 이름에 들어가니 필수는 아니다.

	---
	title: 여기에 글 제목을 입력한다
	layout: post
	---
	
	이제 여기에 글 내용을 입력한다.

위와 같이 입력하면 된다. 이렇게 글을 입력하고 파일을 _post에 저장하고 add, push 했으면 Jekyll 블로그에서 글이 어떻게 보이는지 확인하는 일만 남았다.

## 이제 시작이다
지금까지 Jekyll과 GitHub pages를 이용해서 정말 아무것도 모르는 초보가 무료로 블로그를 하나 만들어 보는 과정을 정리했다. 혹시나 이 글이 다른 사람에게도 도움이 되면 정말 좋겠다.