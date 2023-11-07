---
title: Utterances를 이용한 댓글기능 추가하기
layout: post
author: Kang Juson
tags: [Git, Mac OS, Utterances]
---
## 1. 준비사항
- GitHub 계정이 필요
- 해당 블로그의 GitHub 저장소가 있어야 함
- GitHub Pages로 호스팅 되는 jekyll 블로그가 구축되어 있어야 함

---

## 2. Utterances 스크립트 설정
 1. Utterances GitHub 앱 설치: [Utterances GitHub App](https://github.com/apps/utterances)로 이동하여 GitHub 블로그 저장소에 대해 App을 설치한다.
 2. 댓글을 위한 GitHub Issue  작성 방식 결정: 댓글을 각각의 포스트에 해당하는 Issue로 관리할지, 또는 다른 기준으로 관리할지 결정
 ---

 ## 3. Utterances 스크립트 추가
 1. Utterances 설정: [Utterances](https://utteranc.es/)에 접속한다. (설치하면 자동으로 접속되기도 한다.) 접속한 뒤에 repository를 입력해 준다.
 ![image error](images/스크린샷 2023-11-06 오후 4.59.38.png)
 설정을 완료하면, HTML `<script>` 태그를 자동으로 생성해 준다. (복사 해두길!)
 ![image error](images/스크린샷 2023-11-06 오후 4.59.58.png)

 2. 블로그 테마에 맞는 위치 선택: 댓글을 표시하고자 하는 위치를 결정한다. 대개 `-layouts/post.html` 파일내에 적당한 위치를 찾는다.

 3. 스크립트 태그 삽입: 아까 복사해둔 `<script>` 태그를 붙여 넣는다.
 ![image error](images/스크린샷 2023-11-06 오후 5.09.11.png)

---

## 3. 변경 사항 반영
 1. 변경 사항을 Git을 통하여 commit 하고 GitHub 저장소에 push 한다.
 2. GitHub Pages가 자동으로 웹사이트를 재구성 하도록한다.(기다린다.) 

---

## 4. 블로그에서 댓글 기능 확인
 1. 본인 블로그 포스트 페이지를 방문하여 Utterances 댓글이 정상적으로 작동하는지 확인한다.
 2. 처음 댓글이 게시되면, GitHub 저장소에 해당 내용이 Issue로 생성된다. 
 ![image error](images/스크린샷 2023-11-06 오후 5.15.27.png)
 ![image error](images/스크린샷 2023-11-06 오후 5.16.13.png)

---

# 주의 사항
 - GitHub Pages 사이트는 Public이어야 하며, 저장소의 Issue가 활성화 되어 있어야 한다.
 - 사용자가 댓글을 작성하려면 GitHub 계정이 있어야 한다.

 ---
 오늘 한 Utterance는 지난번에 Ruby를 설치하거나 GitHub Pages를 열거나 하는것 보단 한참 쉬웠다. 제발 다음 할 것도 이러기를.

## P.S.
내 테마에서 Utteracnes를 추가 했는데 댓글을 달려고 보니 Github 로그인이 안되어서 살펴보니 `_config.yml` 파일에 url 부분을 내 주소로 변경하니 해결 되었다.