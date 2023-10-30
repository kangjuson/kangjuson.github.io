---
title: Git 설치하기
layout: post
author: Kang Juson
tags: [Git, Mac OS]
---

# Mac OS에 git 설치하기
Mac OS에 git을 설치하기 위해선 먼저 brew를 설치해야 한다.

아래의 코드를 터미널에 복사해준다. 물론 [HomeBrew](https://brew.sh) 홈페이지에서 복사해도 된다.

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- **기존 Homebrew 경로는 인텔맥 기준이라 애플 실리콘을 사용한다면 경로를 변경해줘야 한다. **
```sh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<USER_ID>/.zprofile
```
```sh
eval "$(/opt/homebrew/bin/brew shellenv)"
```
- 경로를 변경해주었으면 `brew help` 를 입력하여 제대로 동작하는지 확인.
