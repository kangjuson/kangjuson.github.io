---
title: Search Console로 Google 검색에 블로그 나오게 만들기
layout: post
author: Kang Juson
tags: [Git, Mac OS, Google, Search Console]
---

# Search Console 시작하기
 Google Search Console에 사이트맵을 등록시켜주지 않으면 아무리 블로그를 열심히 만들어봤자 검색해도 안나온다. 그렇기 때문에 구글 검색에서 우리의 블로그를 띄우기 위에 오늘은 Search Console을 이용하여 사이트 맵을 등록해 줄 것이다.

---

## 1. 준비하기
 - 아래의 코드를 복사하여 `sitemap.xml` 이라는 파일을 만들어서 본인의 `github.io` 파일 안에 넣는다.

   ```xml
      ---
      layout: null
      ---
      <?xml version="1.0" encoding="UTF-8"?>
      <urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
            xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd"
            xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
         {% for post in site.posts %}
         <url>
            <loc>{{ site.url }}{{ post.url }}</loc>
            {% if post.lastmod == null %}
            <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
            {% else %}
            <lastmod>{{ post.lastmod | date_to_xmlschema }}</lastmod>
            {% endif %}
            {% if post.sitemap.changefreq == null %}
            <changefreq>weekly</changefreq>
            {% else %}
            <changefreq>{{ post.sitemap.changefreq }}</changefreq>
            {% endif %}
            {% if post.sitemap.priority == null %}
            <priority>0.5</priority>
            {% else %}
            <priority>{{ post.sitemap.priority }}</priority>
            {% endif %}
         </url>
         {% endfor %}
      </urlset>
   ```

 - 아래의 코드를 복사하여 `robots.txt` 파일을 만들어 본인의 `github.io` 파일안에 넣는다.

 ```
   User-agent: *
   Allow: /
   Sitemap: {{ '/sitemap.xml' | relative_url | prepend: site.url }}
 ```

 - 파일을 add 하고 commit 한 후 push 해준다.

## 2. 등록하기
1. [Google Search Console 홈페이지](https://search.google.com/search-console/about)에 접속한다.
 ![image error](images/스크린샷 2023-11-15 오후 5.01.17.png)

2. 시작하기를 눌러 다음 페이지로 넘어간 후 좌측 메뉴에서 sitemap 메뉴로 들어간다.
 ![image error](images/스크린샷 2023-11-15 오후 5.01.33.png)

3. 새 사이트맵 추가 메뉴에서 본인 블로그 주소 뒤에 `sitemap.xml` 을 입력한 뒤 제출을 누른다.
 ![image error](images/스크린샷 2023-11-15 오후 5.01.39.png)

---

이러면 아마도? 구글에 검색을 하면 검색어에 따라서 검색결과에 뜰 것이다. 물론 나는 귀찮아서 굳이 찾아보지는 않겠지만 궁금하면 찾아보는 것을 추천한다.
