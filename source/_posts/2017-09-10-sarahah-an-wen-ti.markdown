---
layout: post
title: "談談 Sarahah 的資安與社會問題"
description: "這篇文章想要談談最近很紅的 APP ，Sarahah ，的資安與社會問題。"
date: 2017-09-10 11:33:19 +0800
comments: true
categories: 隨筆 短評
image.feature: 
image.credit: 
image.creditlink: 
image.background: 
external_url: 
ogp_image: https://www.sarahah.com/img/Sarahah-rich.png
published: true
---

這篇文章想要談談最近很紅的 APP ，Sarahah ，的資安與社會問題。

<!--more-->

Sarahah 是一個匿名信箱的應用。註冊 Sarahah 的用戶可取得一個能讓他人（不管寄信者是否登入 Sarahah）匿名寄信給自己的網址，並在 APP 上查閱這些訊息。這像是匿名悄悄話的設計很快地竄紅起來。

但 Sarahah 真的有那麼**匿名**嗎？

# Sarahah 會上傳你的全部聯絡人資料

8 月 28 日，資安顧問公司 Bishop Fox 的分析員 Zach Julian [指出](https://www.bishopfox.com/blog/2017/08/hot-new-anonymous-chat-app-hijacks-millions-contact-data/)，一旦你允許 Sarahah 取得你的聯絡人資料， Sarahah 就會在未經用戶允許，也未告知利用方式的情況下，上傳用戶所有的電話簿和電子郵件地址。

它怎麼取得你的聯絡人資料的？不管是 Android （6+）還是 iPhone 手機，基本上都有這樣的保護機制：除非你另外手動允許 APP 存取你的聯絡人資料，否則 APP 無法將這些資料帶走。所以，基本上它還是會問你「是否允許 Sarahah 存取你的聯絡人資料」。如果你沒有「啊幹你要存取這幹嘛」的一絲懷疑，你就可能因為習慣而允許它的要求。

Julian 的發現不只是一個謠言， Sarahah 的創辦人 Tawfiq 承認了這個機制，[並回應](https://twitter.com/ZainAlabdin878/status/901812205741629444)：這是為了將來要開發的新功能（「找到你的朋友」、「真心悄悄話」之類的）做準備，並且他擔保，目前並未儲存任何一個這樣上傳的資料，他好像也同意這不太好，因此承諾會在下一個更新版將這上傳的動作移除。

# Sarahah 可能會揭露寄件者的身份

除了這資安問題外， Tawfiq 也在[ indiatoday 的一次訪談](http://indiatoday.intoday.in/technology/story/sarahah-can-reveal-your-identity-if-required-says-app-creator-tawfiq/1/1027926.html)中承認，如果有必要，他們會揭露使用者的身份（包括登入的寄件者）。

這意思是說，在 Sarahah 網站上的「Sarahah 不會在登入寄件者未同意的情況下對收件者揭露他們的身份（Sarahah won't disclose the identity of the logged-in senders to users except with their consent）」的政策，具有例外狀況。

之所以 Tawfiq 會承認這一點，卻是為了因應在美國出現的「[ Sarahah 網路霸凌現象](https://nakedsecurity.sophos.com/2017/08/11/latest-viral-sensation-app-sarahah-raises-concerns-about-cyberbullying/)」，社會發現，有些人因收到海量的、持續的惡意攻擊言論而不堪其擾或深受折磨。

這問題並不只是擔憂，[在今年 5 月](http://www.dailymail.co.uk/news/article-4524112/Schools-urgent-warning-dangerous-app.html)，有一起 15 歲英國青少年自殺事件就被認為是與匿名回饋軟體 Sayat.me 有所關聯。

但是，由於非登入者依然能寄匿名信給使用者，這樣的防範機制是否真能有用就很令人懷疑了。

# 最後

順帶一提， Sarahah 並非點對點加密（End-to-End Encryption）通訊軟體[^1]。點對點加密下，寄件者寄出的東西，只有他和收件者兩個人看得懂，其他人拿到都是亂七八糟的密碼。因為解碼方式很複雜，不怕這些東西在「中間」（像和你使用同一個無線網路的人）被擷取。

我目前還不認為「任何人都不應該玩 Sarahah」，但是這似乎是一個不錯的機會，讓我們從這一個例子來想想關於科技與社會的議題，並且對資安多一些警惕和思考。

每當有人要「要求存取」的時候，多想一下「它要幹嘛？」總沒什麼壞處。

# Notes

[^1]: 關於通訊軟體的安全性問題，可以參考[國際特赦組織的報告](https://www.amnesty.org/en/latest/news/2016/10/snapchat-skype-among-apps-not-protecting-users-privacy/)。