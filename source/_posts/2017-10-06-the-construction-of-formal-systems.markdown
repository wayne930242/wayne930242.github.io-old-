---
layout: post
title: "三、形式系統的建構：概述"
description: 本文為演繹邏輯系統之形式化第三章的課堂筆記。
date: 2017-10-06 14:28:40 +0800
comments: true
categories: 邏輯學 筆記 演繹邏輯系統之形式化
image.feature: 
image.credit: 
image.creditlink: 
image.background: 
external_url: 
ogp_image: 
published: false
---

> 本文為演繹邏輯系統之形式化第三章的課堂筆記。

<!--more-->

# A. 公理、假設、變換規則與推導

**A1. 定義 3.1：推導**

$\mathcal{T}$ 是一個形式系統，包含句式的構成規則、一個公理集合 $\mathcal{A} (\mathcal{T})$ （可以是空集合）與一些推理規則 $R(\mathcal{T})$ （又稱「變換規則」）。

令 $\Gamma$ 是 $\mathcal{T}$ 的句式的集合。如果我們說語句序列 $\\{ \alpha _ 1, \cdots , \alpha _ n \\}$ 是的 $\alpha _ n$ 從 $\Gamma$ 在 $\mathcal{T}$ 中的推導，意思是，對於每個 $i(1 \le i \le n)$ 都滿足以下之一：

1. $\alpha$ 屬於 $\mathcal{A}$ 。
2. $\alpha \in \Gamma$ （$\alpha$ 是假設）。
3. $\alpha _ i$ 是 $\alpha _ c$ 與 $\alpha _ d$ （或單單 $\alpha _ c$）（$c, d < i$）的直接 ($R$)-結果。

我們將這寫作 $\Gamma \vdash _ {\mathcal{T}} \phi$ 。

**A2. 定義 3.2：推導樹（derication-tree）**

一個 $\phi$ 的從 $\Gamma$ 在 $\mathcal{T}$ 中的推導被稱作一個 $\phi$ 的推導樹，意思是它符合以下條件：

1. 這圖是一個 2 元樹（$2$-ary tree[^1]），其中每個節點都是一個句式。
2. 這樹將 $\phi$ 當作它的根的句式；
3. 樹的每個葉的句式要嘛屬於 $\mathcal{A}$ 要嘛屬於 $\Gamma$ ；
4. 除了葉外，所有節點的句式都是父節點的句式的直接 ($R$)-結果。

**A3. 定義 3.3：語法序列**

1. 如果 $\Gamma \vdash _ {\mathcal{T}} \phi$ ，我們就說 $\phi$ 是從 $\Gamma$ 可推導的；或說 $\phi$ 是 $\Gamma$ 在 $\mathcal{T}$ 的一個（語法）結果；或說 $\Gamma$ 語法地導衍（syntactically entails） $\phi$ 。
2. 如果 $\Gamma$ 是空集合且 $\Gamma \vdash _ {\mathcal{T}} \phi$ ，我們就說 $\phi$ 是 $\mathcal{T}$ 的一個定理，寫作 $\vdash _ {\mathcal{T}} \phi$。

**A4. 定義 3.4：推導的幂級（the degree of a derivation）**

$\phi$ 的推導的冪級，寫作 $d(\phi)$ 是一個從句式對應到自然數的函數，定義為：

$$\begin{cases} d(\phi) = 1 ，若 \phi 是公理或假設 \\ d(\phi) = d(\psi) +1 ，若 \phi 是 \psi 的直接結果 \\ d(\phi) = 1 + max(d(\psi), d(\theta))，若 \phi 是 \psi 與 \theta 的直接結果 \end{cases}$$

# B. 形式系統的基本語法性質：結構規則、推論規則與一致性

**B1. 定義 3.5：語法的一致性**

1. 一個形式系統 $\mathcal{T}$ 是（推導地、語法地）一致的，若且唯若不存在一個句式 $\phi$ ，使得 $\vdash _ \mathcal{T} \phi$ 並且 $\vdash _ \mathcal{T} \lnot \phi$ ，寫作 $\mathcal{T} \nvdash$ 。否則， $\mathcal{T}$ 是不一致的，寫作 $\mathcal{T} \vdash$ 。
3. 如果對於所有句式 $\phi$ ，都不會是 $\vdash _ {\mathcal{T}} \lnot\phi$ ，那麼我們就說， $\mathcal{T}$ 是絕對一致的（absolutely consistent）。

**B2. 性質 3.1（需要 *MP* 規則）**

1. $\Gamma \vdash \phi$ ，若且唯若 $\Gamma, \lnot \phi, \vdash$。
2. $\Gamma \vdash \lnot \phi$ ，若且唯若 $\Gamma, \phi, \vdash$。
3. 若 $\mathcal{T}$ 是不一致的，那麼對於所有 $\phi, \psi$ ， $\vdash _ {\mathcal{T}} (\lnot \phi \to (\phi \to \psi))$ 。

# C. 形式系統的健全性

**C1. 定義 3.6：系統的健全性（soundness）**

系統 $\mathcal{T}$ 是健全的，若且唯若，若 $\Gamma \vdash _ {\mathcal{T}} \phi$ ，則 $\Gamma \models \phi$ 。

這等價於：

1. 若 $\vdash _ {\mathcal{T}} \phi$ ，則 $\models \phi$ 。
2. 若 $\Gamma \vdash _ {\mathcal{T}}$ ，則 $\Gamma \models$ 。

**C2. 定義 3.7：擴充與子系統（subsystem）**

系統 $\mathcal{T ^ +}$ 是系統 $\mathcal {T}$ 的擴充，若且唯若 $R(\mathcal{T}) \subset R(\mathcal{T ^ +})$ 且 $\mathcal{A} (\mathcal{T}) \subset \mathcal{A} (\mathcal{T ^ +})$ 。這時，我們說 $\mathcal {T}$ 是 $\mathcal {T ^ +}$ 的子系統。

**註記**：若要證明 $\mathcal{T}$ 是健全的，我們只需要證明它是一個健全系統的子系統。

# D. 形式系統的完備性

**D1. 定義 3.8：系統的完備性（completeness）**

系統 $\mathcal{T}$ 是完備的，若且唯若，若 $\Gamma \models \phi$ ，則  $\Gamma \vdash _ {\mathcal{T}} \phi$。

這等價於：

1. 若 $\models \phi$ ，則  $\vdash _ {\mathcal{T}} \phi$ 。
2. 若 $\Gamma \models$ ，則  $\Gamma \vdash _ {\mathcal{T}}$ 。

**D2. 定義 3.9：最大一致集合（maxically consitent）**

一個語句集合 $\Gamma$ 是在 $\mathcal{T}$ 最大一致的，若且唯若 $\Gamma$ 在 $\mathcal{T}$ 是一致的，並且對於每個在 $\mathcal{T}$ 一致的集合 $\Delta (\supset \Gamma)$ ，$\Delta = \Gamma$ 。

**D3. 性質 3.2**

若 $\Gamma$ 是最大一致的語句集合，則：

1. 對於所有 $\Delta \subset \Gamma$ ，若 $\Delta \vdash \phi$ ，則 $\phi \in \Gamma$ 。也就是說， $\Gamma$ 是推導封閉的（closed under derivability）。
2. 對於所有 $\phi$ ，要嘛 $\phi \in \Gamma$ ，要嘛 $\lnot \phi \in \Gamma$ 。

**D4. 引理 3.1**

令 $\mathcal{T}$ 是健全的形式系統。如果存在一個結構使得 $\Gamma$ 的所有句式都為真，那麼 $\Gamma$ 在 $\mathcal{T}$ 中是一致的。

**D5. 引理 3.2：擴充引理**

對於一個一致的句式集合 $\Gamma$ ，存在一個 $\Gamma ^ * (\supset \Gamma)$ 並且 $\Gamma ^ *$ 是最大一致的。

*Proof.*

任何語言的句式都是良序的，我們可令語言內的所有句式為 $\phi _ 1 , \phi _ 2 , \cdots , \phi _n , \cdots$ 。

定義 $\Gamma _ n$ ：

1. $\Gamma _ 0 = \Gamma$
2. $n > 0$: $\Gamma _ n = \begin{cases} \Gamma _ {n-1} \cup \\{\phi _ n \\} ，若這是一個一致集合； \\ \Gamma _ {n-1} ，其他情況。\end{cases}$

令 $\Gamma ^ * = \bigcup _ {n \ge 0} \Gamma _ n$ 。

令 $\Delta$ 是任意一個一致的集合，使得 $\Gamma ^ * \subset \Delta$ 。

假設存在一個 $m$ 使得 $\phi _ m \in \Delta$ 且 $\phi _ m \notin \Gamma ^ *$ 。則 $\phi _ m \notin \Gamma _ m$，亦即 $\Gamma _ m \cup \\{ \phi _m \\}$ 是不一致的，則 $\Delta$ 是不一致的。因此，不存在這樣的 $m$ 。

因此 $\Gamma ^*$ 是最大一致的，並且顯然 $\Gamma \subset \Gamma ^ *$ 。

**D6. 引理 3.3：結構存在引理**

若 $\Gamma \nvdash$ ，則 $\Gamma \nvDash$ 。

*Proof.*

令 $\Gamma ^ *$ 是 $\Gamma$ 的最大一致的擴充，建構方式如 D5 的證明。

我們定義賦值函數 $v$ ：

對於任何原子語句 $P$ ，$v(P) = 1$，若且唯若 $P \in \Gamma _ n$ 。可以數學歸納法證明， $v(\phi)=1$ ，若且唯若， $\phi \in \Gamma ^ *$ ，亦即， $\Gamma ^ * \nvDash$ ，因此 $\Gamma \nvDash$ 。

**D7. 系理 3.1**

$\Gamma \nvdash \phi$ ，若且唯若存在一個結構 $\mathscr{M}$ 使得每個 $\Gamma$ 中的句式在 $\mathscr{M}$ 中為真， $\phi$ 在 $\mathscr{M}$ 中為假，亦即， $\Gamma \nvDash \phi$ 。

*Proof.*

$\Gamma \nvdash \phi$ ，若且唯若 $\Gamma \cup \\{ \lnot \phi \\} \nvdash$ ，若且唯若 $\Gamma \cup \\{ \lnot \phi \\} \nvDash$ ，若且唯若， 存在一個結構 $\mathscr{M}$ 使得每個 $\Gamma \cup \\{ \lnot \phi \\}$ 中的句式在 $\mathscr{M}$ 中為真。

**D8. 定理 3.1：完備性定理**

若 $\Gamma \vDash \phi$ ，則 $\Gamma \vdash \phi$ 。

*Proof.*

定理 3.1 等價於系理 3.1 。

**D9. 引理**

1. 對於每個語句字母 $P_i$ ，若 $\Gamma, P_i \vdash _ {\mathcal{T}}$ ， $\Gamma, \lnot P_i \vdash _ {\mathcal{T}}$ ，則 $\Gamma \vdash _ {\mathcal{T}}$ 。
2. $P_1, \cdots , P_k$ 是在語句 $\phi$ 中出現的每個語句字母，令 $\pm P$ 代表類原子句式，則要嘛 $\phi, \pm P_1, \cdots , \pm P_k \vdash _ {\mathcal{T}}$ ，要嘛 $\pm P_1, \cdots , \pm P_k \vdash _ {\mathcal{T}} \phi$ 。

*Proof. of (1)*

若 $\Gamma \nvdash _ {\mathcal{T}}$ 。

假設存在 $P$ 使得 $\Gamma, P \vdash _ {\mathcal{T}}$ 且 $\Gamma, \lnot P \vdash _ {\mathcal{T}}$ 。則 $\Gamma \vdash _ {\mathcal{T}} \lnot P$ 且 $\Gamma \vdash _ {\mathcal{T}} P$ （根據健全性定理與完備性定理）。矛盾。

因此對於所有 $P$ ， $\Gamma, P \nvdash _ {\mathcal{T}}$ 或 $\Gamma, \lnot P \nvdash _ {\mathcal{T}}$ 。

*Proof. of (2)*

令 $v$ 是一個賦值函數，使得 $\phi, \pm P_1, \cdots \pm P_k$ 的函數值都為真。由於語義的真值函數性， $\phi$ 的真值被唯一決定。

若 $v(\phi) = 1$ ，則 $\pm P_1, \cdots , \pm P_k \vDash \phi$ ，則根據完備性定理， $\pm P_1, \cdots , \pm P_k \vdash \phi$ 。

若 $v(\phi) = 0$ ，則 $\phi, \pm P_1, \cdots , \pm P_k \vDash$ ，則根據引理 3.3， $\phi, \pm P_1, \cdots , \pm P_k \vdash$ 。

**D10. 定理 3.2：（語法的）緊緻性定理**

若 $\Gamma \vdash$ ，則存在有限集合 $\Gamma ^ * \subset \Gamma$ ，使得 $\Gamma ^ * \vdash$ 。

# E. 純語法的完備性（E. Post (1921)）

**E1. 定義 3.10： Post 的完備性定義**

1. 一個系統 $\mathcal{T}$ 被稱作是完備的，那麼，對於每一個 $\phi$ ，要嘛 $\vdash \phi$，要嘛 $\\{ \phi \\} \cup \mathcal{A} (\mathcal{T}) \vdash$ 。
2. 一個系統 $\mathcal{T}$ 被稱作是絕對完備的，那麼，對於每一個 $\phi$ ，要嘛 $\vdash \phi$，要嘛存在一個 $\psi$ 使得 $\\{ \phi \\} \cup \mathcal{A} (\mathcal{T}) \vdash \lnot \psi$ 。
3. 一個系統 $\mathcal{T}$ 被稱作是在給定變換 $\mathcal{R} (\mathcal{T})$ 的考慮下是完備的，那麼，對於每一個 $\phi$ ，要嘛 $\vdash \phi$，要嘛 $\\{ \phi \\} \cup \mathcal{A} (\mathcal{T}) \vdash$ 。

**E2. 定義 3.11：可決定性**

1. $\mathcal{L}$ 的語句 $\phi$ 在 $\mathcal{T}$ 中是可決定的，若且唯若， $\vdash _ {\mathcal{T}} \phi$ 或 $\vdash _ {\mathcal{T}} \lnot \phi$ ；否則， $\phi$ 是不可決定的。
2. 若 $\mathcal{L}$ 的語句集合 $\Gamma$ 中的所有語句在 $\mathcal{T}$ 中都是可決定的，我們就說， $\Gamma$ 是可決定的；否則 $\Gamma$ 是不可決定的。

# F. Gödel 的不完備性定理

**F1. 定理 3.3：Gödel 的第一不完備性定理**

對於任何一個一致的形式系統 $\mathcal{T}$ ，都存在 $\mathcal{T}$ 的語句 $\phi$ 使得 $\phi$ 是不可決定的。

**F2. 定理 3.4：Gödel 的第二不完備性定理**

沒有系統足以證明它自己的一致性。

**F3. 定理 3.5： Church 的理論**

一階述詞邏輯是不可決定的。

# Notes

[^1]: 這意謂著這是有向的、有根的、由節點與有向線段構成的樹的圖形。