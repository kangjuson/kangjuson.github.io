---
title: jekyll 테마 적용하기
layout: post
author: Kang Juson
tags: [jekyll, Github, Blog]
---

## 테마 선택하기

1. [jekyll Themes](http://jekyllthemes.org)에서 본인이 원하는 테마를 선택한다.
2. 마음에 드는 테마를 선택했다면, 해당 테마의 github 페이지로 이동하여 사용 방법과 라이선스를 확인한다.

---

## 테마 적용하기

1. 테마마다 필요한 설정이 다를 수 있으므로 해당 테마의 github 페이지에서 확인한다.
2. 작성자는 [Moonwalk](http://jekyllthemes.org/themes/moonwalk/) 테마를 적용하는 것을 기준으로 할 것이다.
3. `_config_yml` 파일에서 title, author, url(본인 블로그 주소), description 내용을 수정한다.
    ![image error](images/스크린샷 2023-12-04 오후 4.47.30.png)
4. 아래에 theme config 라는 것이 있는데 옆에 설명을 읽고 원하는 것들은 변경 하도록 한다. (작성자는 아무것도 건들지 않았다.) 
    ![image error](images/스크린샷 2023-12-04 오후 4.46.21.png)
5. 작성자는 home: 에서 Post, History, Old project 가 나오도록 내용을 수정하였다.
    ![image error](images/스크린샷 2023-12-04 오후 4.44.58.png)
6. `about.md` 파일에서 블로그에 관한 내용을 작성 하였다.

---

## 로컬에서 블로그 확인

1. 터미널에서 다음 명령어를 실행하여 로컬 서버를 시작한다.(moonwalk 테마 기준)
```sh
bin/start
```
moonwalk 테마가 아니라면 아래의 명령어를 실행한다.
```sh
bundle exec jekyll serve
```

2. 웹 브라우저에서 터미널에 표시된 주소로 접속하여 블로그와 적용된 테마를 확인한다.

---

## 변경 사항을 Github에 Push하기

1. 테마 적용 및 설정 변경 사항을 Git을 통해 commit 하고, Github 저장소에 Push 한다.
2. 시간이 지나면 적용이 될 것이다.

---

## 후기

사실 테마를 적용할때 url도 수정안하고 이것저것 수행을 안하고 해서 시행 착오가 많았지만 이 글을 보는 사람들은 수정해야 할것들 제때 수정해서 나처럼 고생 안하길 바란다.

