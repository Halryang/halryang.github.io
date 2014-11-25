---
layout: post
title: Delete TimeMachine Backup
date: 2014-11-17 16:24:14
summary: OS X에서 외장하드에 저장했던 타임머신 백업 지우는 방법
tags: os-x-tip
---
1. OS X에서 휴지통이 비워지지 않을 때, terminal에 `sudo rm -rf` 라고 적고, 터미널로 지워지지 않는 폴더를 드래그 앤 엔터.
2. 외장하드 타임머신 백업은 위의 방법으로 안된다. 터미널에서 백업에 사용했던 volume으로 `cd /Volumes/Volume이름` 들어가서 `sudo rm -rf .Trashes` 엔터. 이때 progress bar 같은 거 없다. 그냥 다시 `$`커맨드 프롬프트 나올때까지 진득하니 기다려야 함.

*from [Time Machine - Troubleshooting E6. Can't empty the trash after deleting backups via the Finder](http://pondini.org/TM/E6.html "Time Machine - Troubleshooting E6. Can't empty the trash after deleting backups via the Finder")*