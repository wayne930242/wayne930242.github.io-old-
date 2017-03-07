---
layout: post
title: "阿羅不可能定理的證明"
date: 2017-03-07 16:54:16 +0800
comments: true
categories: 經濟學
ogp_image: 
published: false
---

這是 Kenneth Arrow 所提出的一個重要理論，在這篇文章將介紹這個理論的證明方式。這裡的證明整理自 John Geanakoplos 的 "Three Brief Proofs of Arrow's Impossibility Theorem" (2005)。

這個證明是數學的，但是在這篇文章中，我會設法寫得讓一般人都能看懂。為了讓懂得數學的讀者能進一步查證，我會在白話文後面留下數學意義的說明。

<!--more-->

# 基本條件

我們現在有的：

* 至少有三個以上的政策選項。

> 由有限集合 $\mathbb{A} = \left\{a, b, ..., c \right\}$ 來表示。

* 有 $N$ 個人。
* 每個人都對這些政策選項有所偏好，譬如說，喜歡 $a$ 政策多於 $b$ 政策。

> 對於每個小於等於 $N $ 的 $i$ ，都有一個對政策的偏好關係 $\succsim_i $ 。
> 
> 更嚴格來說，我們要求它們的偏好關係都具有完備性和傳遞性。也就是說：
> 
> * 完備性： $\forall a, b \in \mathbb{A}$ ，要嘛 $ a \succsim b$ ，要嘛 $ b \succsim a$ 。
> * 傳遞性： $\forall a, b, c \in \mathhb{A}$ ，如果 $ a \succsim b$ 且 $ b \succsim c$ ，則 $ a \succsum c$ 。
>
> 一個備註

## 舉例

這裡有一個山坡地，山坡地上住了老婆婆、桃太郎和猴子，他們正在決定要在山坡地上蓋什麼。他們有三個政策選項，分別是「種桃子」、「蓋游泳池」和「蓋花果山」。

每個人都對這些選項有自己的偏好。對於老婆婆來說，她的偏好順序從高到低是「種桃子，蓋花果山，蓋游泳池」。桃太郎是「蓋游泳池，種桃子，蓋花果山」。猴子是「蓋花果山，種桃子，蓋游泳池」。


