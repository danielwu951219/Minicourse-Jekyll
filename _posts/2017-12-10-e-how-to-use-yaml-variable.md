---
layout: post
author: Daniel
title: V 如何使用Yaml變數?-  使用Shopify的 Liquid Language
---

Liquid Langeage 是Shopify以ruby所寫的語言，簡單易懂，只要用條件句if,for,else,搭配Liquid Langeage的filter就可以寫出迴圈。以下我們會先介紹基本的語法，再透過實例介紹幾個常用於網站中的迴圈:
##### 基本用法
**I** **引入變數**  
用兩層大括號`{{ "{{ 變數名稱 " }}}}`，將先前在Config.yml或Front matter定義好的變數引入網頁中。

**II** **迴圈**  

 以`for`定義範圍,再以`if`設定條件，最後以`{{ "{% endfor " }}%}`,`{{ "{% endif " }}%}`關閉迴圈

```
{{ "{% for...in... " }}%}
{{ "{% if... " }}%}
...
...
...
{{ "{% endif " }}%}
{{ "{% endfor " }}%}
```

##### 實例介紹
**I** 列出所有category屬於"A"的文章"標題"  
先假設某篇文章的Front matter為:

```
---
layout: post
title: my-first-post
category: A
published: true
---

```
寫一個迴圈
```
{{ "{% for post in site.posts " }}%}
{{ "{% if post.category contains" }}"A" %}

<a href="{{ "{{ post.url " }}}}">{{ "{{ post.title " }}}}</a>

{{ "{% endif " }}%}
{{ "{% endfor " }}%}

```
output:

```
my-first-post
```

**II** 藉由引入include 資料夾的檔案，寫出一個頁面layout，首先必須先了解一個網站頁面的結構:

```
<!DOCTYPE html>
<html>
<head>
...
...
..
</head>

<body>

<header>
...
...
...
</header>

<footer>
...
...
...
</footer>

</body>

</html>
```

可以看見網站主要由 `<head>` `<body>` `<header>` `<footer>` 所組成，Jekyll的好處是讓網站開發者可以將這些網頁組成要數分別以不同的html檔存在`include`資料夾中，再用Liquid Language引入同一個html檔案中。  
以下用一個Layout舉例:  
假設 `head.html` `header.html` `footer.html` 已經寫成html檔存在`include`資料夾中
```
<!DOCTYPE html>
<html>
{{ "{% include head.html " }}%}
<body>
{{ "{% include header.html " }}%}
{{ "{{ content " }}}}
<footer>
{{ "{% include footer.html " }}%}
</footer>
</body>
</html>

```
我們把以上code存成html檔，命名為`default.html`，當我們要寫新的post或page時，我們便可以直接在Front Matter 宣告 `layout: default`,接著只需寫該頁面的`特定內容`(`{{ "{{ content " }}}}`) :  

```
---
layout: default
---
內容可以用html或markdown撰寫
...
...
...

```
---

## Practice 2
1. 在`_posts`資料夾中，先製作兩篇posts(注意命名方式)，並在fontmatter中設定`category: A`
2. 在`practice2.html`利用liquid language與html語法，用清單的方式列出category為A的文章
3. 最後在`practice2.html`中，利用liquid language 將`_includes`資料夾中`youtube.html`引入該頁面中。
<br>
完成後，你所製作的頁面將會出現在網站右上角的`Practice`連結內。
