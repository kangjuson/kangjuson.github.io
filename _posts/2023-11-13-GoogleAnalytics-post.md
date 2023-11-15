---
title: Google Analytics를 Jekyll 블로그에 적용하기
layout: post
author: Kang Juson
tags: [Git, Mac OS, Google, Analytics]
---
Google Analytics는 웹사이트의 트래픽을 분석하고 사용자의 행동을 이해하는 데 도움을 주는 서비스이다. 이를 Jekyll 블로그에 적용하면 방문자의 활동을 추적하고 분석할 수 있다.

---
# 설정단계

---

## 1. Google Analytics 계정 설정
 1. [Google Analytics 웹사이트](https://analytics.google.com/)로 이동하여 로그인하거나 계정을 생성한다.
 
 2. 관리 탭으로 이동하여 새로운 계정을 생성한다.
    ![image error](images/스크린샷 2023-11-13 오후 5.18.57.png)

 3. 새 웹사이트에 대한 속성을 설정한다.

    ![image error](images/스크린샷 2023-11-13 오후 5.21.17.png)

 4.  비지니스 설명에 대해선 그냥 하고 싶은 대로 하면 된다.
     ![image error](images/스크린샷 2023-11-13 오후 5.22.02.png)

 5. 비지니스 목표는 기준 보고서 보기 로 설정해 준다.
     ![image error](images/스크린샷 2023-11-13 오후 5.23.21.png)

 6. 웹사이트를 입력한다.
     ![image error](images/스크린샷 2023-11-13 오후 5.25.02.png)

 4. 추적 ID를 받는다.
   ![image error](images/스크린샷 2023-11-13 오후 5.25.21.png)

---

## 2. Jekyll 블로그에 추적코드 추가
 1. Jekyll 사이트의 `_config.yml 파일을 연다. (없는 경우 3번으로)
 2. analytics 관련 설정이 있는지 칮아보고, 적절히 수정한다.
 3. Google Analytics 추적 코드를 포함할 설정이 없는 경우, 직접 HTML 파일을 설정한다. 보통은 `_includes` 폴더 내의 `head.html` 파일을 사용한다.
 4. `head.html` 파일을 열고, 위에서 복사한 추적 코드 스니펫을 `</head>` 태그 바로 앞에 붙여넣는다.
   ![image error](images/스크린샷 2023-11-15 오후 4.43.53.png)

   ```html
   <--! Google tag (gtag.js) -->
   <script async src="https://googletagmanager.com/gtag/js?id=G-
   HH2DRPJVWC"></script>
   <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());

      gtag('config', 'G-HH2DRPJVWC');
   <script>
   ```
   ![image error](images/스크린샷 2023-11-15 오후 4.43.41.png)

 5. 모든 변경 사항을 저장하고 GitHub에 커밋 및 푸시한다.

 ---

# Google Analytics 사용하기

 ---

 설정 후 Google Analytics는 자동으로 데이터를 수집하기 시작한다. 수집된 데이터를 보려면 다음 단계를 따라야 한다.
  1. [Google Analytics 대시보드](https://analytics.google.com/) 로 이동한다.
  ![image error](images/스크린샷 2023-11-15 오후 4.46.41.png)

  2. 좌측 메뉴에서 실시간을 클릭하여 실시간 방문자 수를 확인하는 등 다양한 섹션에서 방문자의 여러 측면을 분석한다.
  ![image error](images/스크린샷 2023-11-15 오후 4.47.01.png)

  3. 대시보드를 사용자 정의 하여 가장 중요한 지표를 한눈에 볼 수 있도록 설정할 수 있다.

---

오늘은 google analytics 를 활용하여 트래픽을 분석할 수 있게 해보았다. 지금은 들어오는 사람이 없겠지만 구글에 사이트를 등록하므로써 구글 검색에 나올 수 있도록 다음에 해보겠다.