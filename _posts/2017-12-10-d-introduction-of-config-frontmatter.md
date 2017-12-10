---
layout: post
author: Daniel
title: IV 什麼是"Config.yml","Frontmatter"?
---
<i class="em em-warning"></i>**請注意 在寫yml格式的檔案時不能用 `tab鍵` 來縮排  !!**  
<br>
Config.yml是Jekyll中很特別的檔案，可以讓網站開發者自行定義變數。Config.yml主要是用來定義全域變數。例如:

```
title:          Jekyll 基礎教學網站
paginate:       10
baseurl:        "/Minicourse-Jekyll"
plugins:
  - jekyll-paginate

```

而Frontmatter也是yaml格式，但是只需要在html檔案的頁首進行宣告，宣告方式如下，比如說，我們會在寫文章時存成md檔，為了要讓jekyll讀懂這篇文章的layout是甚麼，以及liquid language所引入的變數是甚麼，我們會在文章的最開始寫上FRONTMATTER，同時在上下以`---`包住，告訴JEKYLL這是一個YAML格式:(以下舉例，變數可以依頁面的需求自行定義):

```
---
layout:
date:
catagories:
tag:
---
```
### 常用的yaml variables
jekyll本身已經預設variables,以下將介紹常用變數的用途:
global variables:
```
site:網站
page:頁面
layout:自行設定的版型
content:頁面內容(front matter宣告後，該頁面的內容)
paginator:分頁工具
```

site variables:
```
site.posts:網站中所有posts的清單
site.pages:網站中所有pages的清單
```
page variables:
```
page.categories:該頁面所屬的categoriies
page.date:該頁面的日期
```
其他變數可以到[JEKYLL的官網](https://jekyllrb.com/docs/frontmatter/)查詢。
