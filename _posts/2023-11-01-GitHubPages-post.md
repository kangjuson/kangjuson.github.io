---
title: GitHub Pages와 Jekyll로 블로그 시작하기
layout: post
author: Kang Juson
tags: [Git, Mac OS, GitHub, Jekyll]
---

## 1. 준비 사항
- GitHub 계정
- VS Code
- Git 설치

---

## 2. GitHub 저장소 생성
 1. GitHub에 로그인한 후, Repository를 생성한다. 저장소 이름은 `username.github.io`로 지정한다.

---

## 3. Jekyll 설치 및 초기 설정
 - Ruby 설치

  우리들의 사랑스러운 Mac에는 기본적으로 Ruby가 설치되어 있다. 하지만 버전이 너무 낮아서 jekyll을 사용하는데에 문제가 생기기 때문에 ruby 버전을 업데이트 시켜줘야 한다.(윈도우는 그냥 [RubyInstaller](https://rubyinstaller.org) 사용하면 된다.)

  업데이트 방법은 굉장히 간단하지 않다. 
 먼저 `brew install rbenv` 로 가장 최신 버전의 rbenv를 설치한다.
 ![image error](images/스크린샷 2023-11-01 오전 11.49.04.png)

 ### rbenv를 통해 Ruby 설치
 아래 명령을 통해서 rbenv로 설치 할 수 있는 Ruby 버전을 확인한다.
 `rbenv install -l`
 ![image error](images/스크린샷 2023-11-01 오전 11.53.14.png)
 리스트에 있는 버전들 중에서 아무거나 하나 골라 설치한다.
 개인적으론 3.1 대의 버전을 설치하는 것을 추천한다.(블로그 테마들 중에 3.1 대의 버전을 가지고 있어서 로컬 서버가 열리는 경우가 종종 있다.) 

 아래의 명령어를 입력하여 설치
 ```sh
 rbenv install 3.1.4
 ```

 설치가 완료되었다면, `rbenv versions` 를 통해 기기에 설치된 Ruby버전을 확인 할 수 있다.
 ![image error](images/스크린샷 2023-11-01 오전 11.59.46.png)

 아래의 명령어를 통해 기본적으로 PowerShell 이 열리면 rbenv에 설치된 Ruby를 가리키도록 바꿔준다.
 (이렇게 안하면 설치한 의미가 없다.)
 ```sh
 rbenv globall 3.1.4
 ```
 ![image error](images/스크린샷 2023-11-01 오전 11.59.46.png)

 이렇게 했음에도 나는 루비 버전이 바뀌지 않았기 때문에 추가적인 과정을 더 거쳤다.

 `rbenv global` 명령어를 실행했음에도, `ruby -v` 으로 확인 했을때 기본버전으로 나왔었다.
 ![image error](images/스크린샷 2023-11-01 오후 12.08.48.png)
 
 이러한 경우엔 환경변수 설정이 필요하다.

 `rbenv init` 명령어를 실행하고 출력되는 eval로 시작되는 줄을 복사하여 준다.
 ![image error](images/스크린샷 2023-11-01 오후 12.10.53.png)
 
 그 후에 아래의 명령어를 입력하여 준다.
 ```sh
 sudo nano ~/.zshrc
 ```
 그렇게 해서 나온 화면에 아까 복사했던 eval 으로 시작하는 명령어를 복사하여 준다.

 (혹시나 안했을 사람들을 위하여)
 ```sh
 eval "$(rbenv init - zsh)"
 ```
 ![image error](images/스크린샷 2023-11-01 오후 12.13.14.png)

 화면과 같이 한 후에 ctrl + x를 눌러 나와준다.

 이 과정이 끝난 후에 다시 `ruby -v` 를 입력해보면,
 ![image error](images/스크린샷 2023-11-01 오전 10.58.15.png)
 
 Ruby 버전이 바뀐것을 확인하여 볼 수가 있다! 

 우리들의 사랑스러운 Mac 덕분에 윈도우랑은 다르게 Ruby 설치하는데에만 이렇게 많은 과정이 필요하다!
 
 (어지간하면 윈도우 써라...)

 - Jekyll 및 bundler 설치

 아래 명령어 입력.
 ```sh
 gem install jekyll bundler
 ```
 ![image error](images/스크린샷 2023-11-01 오전 10.41.57.png)

 - 새로운 Jekyll 사이트 생성
 ```sh
 jekyll new username.github.io
 ```
 - 생성된 디렉토리로 이동
 ```sh
 cd username.github.io
 ```
---

## 4. VS Code로 프로젝트 열기
1. VS code를 연다
2. 파일 > 폴더 열기 > 위에서 생성한 Jekyll 사이트 디렉토리 선택

--- 

## 5. Git 연동 및 GitHub에 Push
1. 터미널에서 다음 명령어를 실행시켜 Git 초기화
```sh
git init
```
2. GitHub 저장소를 remote로 추가
```sh
git remote add origin https://github.io/username/username.github.io.git
```
3. 파일들을 commit 하고 GitHub에 Push
```sh
git add -A
git commit -m 'Initial commit'
git push -u origin main
```

---

## 6. 블로그 확인
아무런 브라우저에서 `https://username.github.io` 로 접속하여 블로그가 정상적으로 동작하는지 확인

(가끔씩 여기까지 하고도 동작하지 않는 경우가 있는데, 그렇다면 테마를 적용하고 확인해보면 되는 경우가 있다.)

---

드디어 길고 긴 과정이 모두 끝이 났다. 진짜 jekyll 깔면서 Ruby 버전이 안맞아서 깔리지도 않고 Ruby를 새로 깔았는데도 버전은 바뀌지도 않는 등 여러가지 시행착오를 거쳤지만 막상 완성하고 나면 뿌듯함을 말로 형용할 수 없을 것이다. 적어도 나는 그랬으니까. 

많은 사람들이 이 Post로 인해서 많은 도움이 되었길 바랍니다. 긴 글 읽어주셔서 감사합니다.

--- 
## P.S.
만약 3.2.X 버전을 깔았는데 3.1.X 버전이 아니여서 로컬 서버가 안열린다면 
`rbenv install 3.1.X `를 한뒤에 `rbenv global 3.1.X`를 해주고
`gem install jekyll` 을 해준 뒤, `bundle install` 을 입력해주고 설치가 끝난 뒤 `bundler exec jekyll serve`를 입력하면 로컬 서버를 열 수 있을 것이다.