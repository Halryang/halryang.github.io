---
title: 압축 파일 빠르게 푸는 Keyboard Maestro Macro
layout: post
date: 2016-12-08 16:15:08
tags: Keyboard-Maestro productivity
---
매우 빠르게 압축 파일을 풀 수 있는 Keyboard Maestro Macro를 소개합니다. [이곳](http://robservatory.com/quickly-expand-compressed-files-in-finder/ "Quickly expand compressed files in Finder :: The Robservatory")에서 얻은 Keyboard Maestro 매크로입니다. 위의 글에서 설명하기로, 24개의 .gz 파일의 압축을 푸는데 macOS의 파인더 GUI상에서 12.8초가 걸렸고, 터미널에서 UNIX 명령어를 사용해서 풀때는 .013초가 걸렸다고 합니다. 터미널에서 압축을 푸는 것이 Finder에서 푸는 것보다 984.6배나 빠르답니다.

하지만 터미널에 익숙하지 않은 사용자에게는 터미널에서 해당하는 파일을 지정해서 압축을 푸는 것이 불편하지요. Keyboard Maestro Macro를 이용하면 파인더에서 압축 파일을 선택하고 Keyboard Maestro Macro를 실행하면 명령어를 모르는 사람도 편하고 빠르게 압축을 풀 수 있습니다. 여기서 소개하는 매크로 중 하나는 .gz 파일을 푸는 것이고, 하나는 다른 확장자로 압축된 파일을 풀 수 있는 것입니다. 매크로는 위의 페이지의 [download both macros](http://robservatory.com/dlfiles/Finder_expansion_macros.zip)
에서 받을 수 있습니다. *모든 압축 파일을 푸는 매크로의 경우 스크립트 파일을 받아서 원하는 위치에 두고 매크로 안에서 경로를 수정해야 작동합니다.*

이 매크로의 단점으로는 가끔 소스 폴더가 아닌 다운로드 폴더에 압축이 풀리는 경우가 생길 수 있고, 압축 형식에 따라 압축된 폴더 구조가 풀릴 수 있다고 합니다.