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
- **우리의 사랑스러운 애플 실리콘 맥에선 기존 인텔 맥과 경로가 다르기 때문에 수정을 해줘야 한다.**
```sh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<USER_ID>/.zprofile
```
```sh
eval "$(/opt/homebrew/bin/brew shellenv)"
```
- 경로를 변경해주었으면 `brew help` 를 입력하여 제대로 동작하는지 확인.

home brew 설치가 끝났다면 이제 git을 설치할 차례이다.

1. [git 홈페이지](https://git-scm.com)에 접속한다.

2. Download for Mac을 클릭한다.
 ![image error](images/스크린샷 2023-11-01 오전 11.22.52.png)

3. 앞에서 homebrew 는 다운을 받았기 때문에 아래 명령어를 입력해준다.
```sh
brew install git
```

4. 설치가 잘 되었는지 확인하기 위해서 아래의 명령러를 입력한다.
```sh
git --version
```
git 버전이 출력된다면 정상적으로 설치된 것이다.