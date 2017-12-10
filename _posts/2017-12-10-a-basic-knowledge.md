---
layout: post
title: I 了解網站的基本架構
author: Daniel
category: A
---

建立一個網站，首先需要具備 網域 主機  網站資料。  
- 網域:每台連上網的電腦都有屬於自己的IP，但IP由數字組成，不方便記憶，於是網域名稱系統(Domain Name System)就誕生了,你可以把IP想像成你的電話號碼，網域名稱(ex.http://emajortaiwan.org)就是你的名子，手機就是Domain Name server，Domain Name System就是電話簿。
- 網站資料:由不同的html檔、css檔組成(簡單的靜態網頁)，html語法是用來呈現網頁的內容，Css語法則是針對html所寫的內容作更進一步的編排、調整(ex.顏色、字體、呈現位置)
- 主機:用來放網站資料

## 這三樣東西如何連結?
首先我們會把網站資料放進主機，再將主機與網域作連結。我們必須告訴主機我們的域名(主機對網址)，同時也要把主機的ip告訴域名商(網址對主機)，當雙向連結完成，我們只要在瀏覽器中搜尋自己的域名就能夠看見網頁了。

## Html、Css 基礎介紹
請見[簡易範例]({{site.baseurl}}/practice1.html)

[推薦][Html與Css的教學網站](https://www.w3schools.com/)
