---
layout: post
title: "二、命題邏輯的諸語義學後設理論"
description: 本文為演繹邏輯系統之形式化第二章的課堂筆記。
date: 2017-10-02 10:26:41 +0800
comments: true
categories: 筆記 邏輯學 演繹邏輯系統之形式化
image.feature: 
image.credit: 
image.creditlink: 
image.background: 
external_url: 
ogp_image: 
published: true
---

> 本文為演繹邏輯系統之形式化第二章的課堂筆記。

<!--more-->

# A. 真值函數： $\mathcal{L}_\mathbf{K}$ 的表達適足性與函數完備理論

**A1. 真值函數**

真值函數是從 n-陣列的（n 元的）真值集合 $\\{T, F\\}^n$ 對應到單一真值集合 $\\{T, F\\}$ 的函數。

在 $\mathcal{L}_ \mathbf{K}$ 中有五個連接符，亦即，有五個真值函數（四個 1-陣列，一個 0-陣列）可以在此語言中直接表述。理論上來說，由於句式可不限使用連接符以及原子語句， $\mathcal{L}_\mathbf{K}$ 中可以有無限多個 n-陣列的真值函數。

**A2. 定義 2.1：表達適足性（experssive adequacy）**

1. 對於一個給定真值函數 $v$ ，如果能只用一個連接符集合 $\Delta$ 中的連接符和原子語句來組成句式表達該函數，我們就說， $\Delta$ 適足表達 $v$ 。
2. 如果一個連接符集合 $\Delta$ 能適足表達在 $\mathcal{L}$ 語言中的每一個真值函數，則我們說 $\Delta$ 是在 $\mathcal{L}$ 中表達地適足簡化的（*expressively adequate simpliciter* ，或函數地完備的，*functionally complete*）。

**A3. 定義 2.2：連接符的可定義性**

1. 一個連接了 n 個句式的連接符 $\oplus$ 在一個語言中稱作是可定義的，若且唯若，存在一個包含單一 $\oplus$ 的句式，使得一個 n-陣列的真值函數可以被這個句式所表達。
2. 一個連接符 $\oplus$ 在一個特殊連接符的集合 $\Delta$ 的語項中是可定義的，若且唯若 $\oplus$ 所表達的真值函數可以由只包含 $\Delta$ 中的連接詞的句式所表達。

**A4. 性質 2.1**

$\\{ \lnot , \land , \lor \\}$ 適足表達每個二元的真值函數。

**A5. 定理 2.1：函數的完備性定理**

$\\{ \lnot , \land , \lor \\}$ 是函數地完備的。

*Proof.*

對於任意的 n-陣列的真值函數 $v$ ，假設 $v$ 定義在 $\\{P_ 1, P_ 2, \cdots P_ n \\}$ 上。

考慮兩種不同的狀況來建立句式：

狀況一、 $v$ 的所有函數值皆為 $F$ 。則可以 $(P_1 \land \lnot P_1)$ 表達 $v$ 。

狀況二、 有 $k$ 個結構（$k \le 2^n$）使得 $v$ 的函數值為 $T$ ，假設這些結構為 $\\{ \mathscr{M}_ {r_ 1}, \mathscr{M}_ {r_ 2}, \cdots \mathscr{M}_ {r_ k} \\}$ 。

對於每一個 $\mathscr{M}_{r_k}$ （$j \le k$），我們可以建立一個這樣的 $\phi_j$：

$$\phi_j: (\pi_1 \land \pi_2 \land \cdots \land \pi_n)$$

在這，對於每個 $i$ （ $1 \le i \le n$ ）：若 $P_i$ 在 $\mathscr{M}_i$ 中為 $T$ ，則 $\pi_i = P_i$ ；否則， $\pi_i = \lnot P_i$ 。

我們所建構的可表達 $v$ 的句式為：

$$\phi: \bigvee_{1 \le j \le k} \phi_j$$[^1]

**A6. 性質 2.2**

$\mathcal{L}_\mathbf{K}$ 的五個連接符的集合是函數地完備的。

# B. 選言標準形式（DNF）與連言標準形式（CNF）

**B1. 定義 2.3：類原子句式**

一個句式被稱作類原子的（quasi-atomic），若且唯若它包含單一的語句字母以及最多一個否定符（$\lnot$）。

**B2. 定義 2.4：DNF 與 CNF**

1. 一個語句如果是選言標準形式的（in DNF, in disjunctive normal form），若且唯若它是準原子句式的連言的選言。
2. 一個語句如果是連言標準形式的（in CNF, in conjunctive normal form），若且唯若它是準原子句式的選言的連言。

**B3. 定理 2.2**

1. 對於 $\mathcal{L}_\mathbf{K}$ 的任何句式 $\phi$ ，存在一個選言標準形式的句式 $\phi^D$ 與 $\phi$ 邏輯地等同。
2. 對於 $\mathcal{L}_\mathbf{K}$ 的任何句式 $\phi$ ，存在一個連言標準形式的句式 $\phi^C$ 與 $\phi$ 邏輯地等同。

*Proof.*

$\phi^D$ 的存在由 **A5** 和 **A6** 可證明。 $\phi^C$ 可從此結論以替代定理、笛．摩根律和分配律加以證明。

# C. 插式定理

**C1. 定理 2.3：插式定理（interpolation theorem）**

若 $\phi \models \psi$ ，則存在句式 $\theta(P)$ （$P$ 同時出現在 $\phi$ 與 $\psi$ 中）使得 $\phi \models \theta$ 且 $\theta \models \psi$ 。此處的 $\theta$ 稱作插式（interpolant）。

若不存在同時出現在 $\phi$ 與 $\psi$ 中的 $P$ ，則要嘛 $\phi \models$ ，要嘛 $\models \psi$ 。

*Proof.*

可以證明，對於每個出現在 $\phi$ 但不出現在 $\psi$ 的 $P_i (\in \\{ P_1 , P_2 , \cdots , P_n \\} )$ ，都有：

1. $\phi(P_i) \models \phi (\top/P_i) \lor \phi (\bot/P_i)$
2. $\phi (\top/P_i) \lor \phi (\bot/P_i) \models \psi$

對於每個 $i \le n$ ，我們定義：

1. $\theta_{P_1} = \phi (\top/P_1) \lor \phi (\bot/P_1)$ 
2. $\theta_{P_i} = \theta_{P_{i-1}} (\top/P_i) \lor \theta_{P_{i-1}} (\bot/P_i)$ 。

$\theta_{P_n}$ 就差不多是我們要找的 $\theta$ ，只需要將 $\theta_{P_n}$ 裡面的 $\top$ 和 $\bot$ 分別用恆真或矛盾的句式來替代。

# D. 命題邏輯的緊緻性

**D1. 定義 2.5：可滿足性**

一個句式集合 $\Gamma$ 是可滿足的（satisfiable），若且唯若，存在一個結構使得所有在 $\Gamma$ 中的句式都為真。

**D2. 定理 2.4：緊緻性定理（Compactness Theorem）**

$\mathcal{L}_\mathbf{K}$ 中的句式集合 $\Theta$ 是可滿足的，若且唯若，每個 $\Theta$ 的有限子集 $\Gamma$ 都是可滿足的。

*Proof.*

唯一需要我們證明的方向是 $(\Leftarrow)$ 。

給定任何一個可滿足的有限句式集合 $\Gamma$ 。由於 $\mathcal{L}_ \mathbf{K}$ 是良序的，我們可令 $\mathcal{L}_\mathbf{K}$ 的所有句式為 $\phi_1, \phi_2, \cdots \phi_n, \cdots$ 。

我們遞迴地定義這樣一個序列：

$$\Delta_0 = \Gamma$$

$$\Delta_{n+1} = \begin{cases} \Delta_n \cup \\{ \phi_{n+1}\\} 如果這是可滿足的； \\ \Delta_n \cup \\{ \lnot \phi_{n+1} \\} 否則。 \end{cases}$$

令 $\Delta = \bigcup_n \Delta_n$ 。

可以看出：

1. $\Gamma \subset \Delta$ 。
2. 對於每一個句式 $\phi$ ，要嘛 $\phi \in \Delta$ ，要嘛 $\lnot \phi \in \Delta$ 。
3. $\Delta$ 的每一個有限子集都是可滿足的。

我們定義一個真值賦值函數 $v$ ：$v(P) = 1 ，若且唯若 P \in \Delta$ ，對於每一個原子句式 $P$ 。

可以數學歸納法證明： $v(\phi)=1，若且唯若 \phi \in \Delta$。

也就是說， $\Delta$ 是可被 $v$ 滿足的。

**D3. 系理：緊緻性理論的變體**

1. 若 $\Gamma \models \phi$ ，則存在一個 $\Gamma$ 的有限子集 $\Gamma'$ 使得 $\Gamma' \models \phi$ 。
2. 若 $\Gamma \models$ ，則存在一個 $\Gamma$ 的有限子集 $\Gamma'$ 使得 $\Gamma' \models$ 。

# E. $\mathcal{L}_ \mathbf{K}$ 的可決定性

**E1. 定義 2.6：有效程序（effective procedure）**

一個有效程序，意指符合以下兩個條件的機制：

1. 由精確規程構成的有限集合，這些規程只具有有限長度，解釋如何機械地按照它執行程序。
2. 沒有隨機的裝置，或任何這樣的裝置在實踐上是只能估計的。

**E2. 定義 2.7：決定程序（decision procedure）**

一個決定程序，意指我們能在有限步驟中應用該程序決定結果的一個有效程序。

**E3. 定義 2.8：可決定性（decidability）**

一個表達的集合 $\Gamma$ 是可決定的，若且唯若存在一個有效程序，給定一個 $\phi$ ，能決定是否 $\phi \in \Gamma$ 。

**E4. 定理 2.5**

1. $\mathcal{L}_ \mathbf{K}$-序列的集合是可決定的；尤其， $\mathcal{L}_ \mathbf{K}$ 的拓樸的集合是可決定的。
2. 對於一個 $\mathcal{L}_ \mathbf{K}$ 的句式的有限集合 $\Gamma$ ， $\Gamma$ 的拓樸結果（tautological consequence）是可決定的。

*Proof.*

真值表法就是一個能決定句式的語義值的決定程序。

# Notes

[^1]: 可以看出，此處的 $\phi$ 是選言標準形式的。