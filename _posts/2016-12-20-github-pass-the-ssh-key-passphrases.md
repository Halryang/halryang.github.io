---
layout: post
title: Pass ssh key passphrase
date: 2016-12-20 00:03:35
tags: ssh github
---
이전에는 GitHub에 ssh를 통해 커밋, 푸시하는 과정에서 passphrase를 따로 물어보지 않았는데, 어제는 이상하게 계속해서 passphrase를 넣으라고 합니다. 그래서 검색했더니 ssh-add를 사용해보라는 답이 있었어요.

그래서 [여기](http://stackoverflow.com/questions/10032461/git-keeps-asking-me-for-my-ssh-key-passphrase)에 있는 답변을 참고해서 `ssh-add` 명령어를 입력했습니다.

이글은 위 명령어로 푸시할 때 passphrase를 안 넣어도 되도록 설정할 수 있는지 시험하는 글이기도 합니다.