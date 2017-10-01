---
layout: post
title: "形式語言與基本語義學"
description: 演繹邏輯系統之形式化第一章的課堂筆記。
date: 2017-10-01 12:52:55 +0800
comments: true
categories: 筆記 邏輯學
image.feature: 
image.credit: 
image.creditlink: 
image.background: 
external_url: 
ogp_image: 
published: true
---

> 本文為演繹邏輯系統之形式化第一章的課堂筆記。

# A.  $\mathcal{L}_\mathbf{K}$ 的建構

我們首先建構關於命題邏輯的一個形式語言，$\mathcal{L}_\mathbf{K}$。

<!--more-->

**A1.** $\mathcal{L}_\mathbf{K}$ 由以下字母所構成：

* (A1) 語句字母（sentence letters）：$P$、$Q$、$R$、$S$、$T$、$P_1$、$P_2$、 ...
* (A2) 連接符（connectives）[^1]：$\lnot$、$\lor$、$\land$、$\to$、$\leftrightarrow$[^2]
* (A3) 輔助字母：$($、$)$

**A2.** $\mathcal{L}_\mathbf{K}$ 蒐集所有的公式（well-formed fomula, *wff*），構成規則（fomation rules）如下：

* (F1) 每個語句字母都是一個公式。（原子語句）
* (F2) 如果 $\phi$ 是一個公式，那 $\lnot \phi$ 也是。
* (F3) 如果 $\phi$ 和 $\psi$ 都是公式，那 $(\phi \lor \psi)$、$(\phi \land \psi)$、$(\phi \to \psi)$、$(\phi \leftrightarrow \psi)$ 也是。
* (F4) 除此之外，沒有其他公式。[^3]

# B. $\mathcal{L}_\mathbf{K}$ 的基本語法學

**B1. 定義 1.1** 構成序列（formation sequences）

若公式序列 $\\{  \phi_1, \phi_2, \cdots , \phi_n \\}$ 被稱作公式 $\phi$ 的構成序列，那：$\phi_n = \phi$ ，[^4]並且對於每個 $k \le n$，恰有以下之一被滿足：

1. $\phi_k$ 是原子語句。
2. 存在 $j<k$，使得 $\phi_k = \lnot \phi_j$
3. 存在 $i, j<k$，使得 $\phi_k = (\phi_i \lor \phi_j)$ 或 $\phi_k = (\phi_i \land \phi_j)$ 或 $\phi_k = (\phi_i \to \phi_j)$ 或 $\phi_k = (\phi_i \leftrightarrow \phi_j)$。

**B2. 定義 1.2** 子公式（subformula）

若公式 $\psi$ 被稱作公式 $\phi$ 的一個子公式，則有以下之一被滿足：

1. $\psi=\phi$ 
2. $\phi=\lnot\psi_i$ 並且 $\psi$ 是 $\psi_i$ 的一個子公式。
3. $\phi$ 符合以下形式之一： $(\psi_i \lor \psi_j)$、$(\psi_i \land \psi_j)$、$(\psi_i \to \psi_j)$、$(\psi_i \leftrightarrow \psi_j)$，其中 $\psi$ 是 $\psi_i$ 或 $\psi_j$ 的一個子公式。

**B3. 定義 1.3** 直接子公式（immediate subformula）

若公式 $\psi$ 被稱作公式 $\phi$ 的一個直接子公式，則有以下之一被滿足：

1. $\phi=\lnot\psi$ 。
2. $\phi$ 符合以下形式之一： $(\psi_i \lor \psi_j)$、$(\psi_i \land \psi_j)$、$(\psi_i \to \psi_j)$、$(\psi_i \leftrightarrow \psi_j)$，其中 $\psi = \psi_i$ 或 $\psi = \psi_j$ 。

**B4. 定義 1.4** 公式的主要連接符（main connective）

如果一個連接符連接了 $\phi$ 的直接子公式，我們就稱此連接符為 $\phi$ 的主要連接符。

**B5. 定義 1.5** 連接符的出現的範圍（the *scope* of an occurrence of a connective）

給定一個公式 $\phi$ ，一個連接符的出現的範圍為 $\phi$ 的一個子公式 $\psi$ ，滿足：

1. 該連接符的出現在 $\psi$ 中；
2. 對於所有 $\psi$ 的直接子集合 $\theta$ ，該連接符的出現不在 $\theta$ 中。

**B6. 定理 1.1** 唯一可讀性定理（分解的唯一性定理）

如果 $\phi$ 是 $\mathcal{L}$ 的一個公式，以下之一恰好成立：

1. $\phi$ 是原子語句；
2. 存在唯一的 $\psi$ ，使得 $\phi = \lnot\psi$；
3. 存在唯一的 $\theta, \psi$ ，使得 $\phi = \theta \land \psi$；
4. 存在唯一的 $\theta, \psi$ ，使得 $\phi = \theta \lor \psi$；
5. 存在唯一的 $\theta, \psi$ ，使得 $\phi = \theta \to \psi$；
6. 存在唯一的 $\theta, \psi$ ，使得 $\phi = \theta \leftrightarrow \psi$。

**[證明方法]** 先定義公式長度的度量方法（一個從公式對應到自然數的函數），並以數學歸納法證明，對於任何長度的公式這性質都成立。

# C. $\mathcal{L}_\mathbf{K}$ 的基本語義學

**C1.** 古典語義學採取以下三個假設（古典假設）：

1. **二值原則（the principle of bivalence）**：公式的真值只有兩種，真或假。
2. **真值函數性原則（the principle of truth-functionality）**：連接詞必須是真值函數（又稱為布林函數， Boolean function）。
3. **擴充性原則（the principle of extensionality）**：任何公式的真值只能由包含其中的原子語句之真值與連接詞決定。

**C2. 定義 1.6** 結構（structure）

我們可以對語句字母進行真值分派，每一個這樣的分派稱作一個結構。我們以 $\mathscr{M}$、$\mathscr{N}$、$\mathscr{A}$、$\mathscr{B}$ 加以表示。[^5]

注意：結構不見得分派每一個語句字母的真假值。

**C3. 定義 1.7** 在結構中被定義

一個公式 $\phi$ 的真值如果在 $\mathscr{M}$ 中被決定，我們就說， $\phi$ 在 $\mathscr{M}$ 中被定義。

如果 $\phi$ 被 $\mathscr{M}$ 決定為真，我們就說， $\phi$ 在 $\mathscr{M}$ 中為真。如果決定為假，我們就說， $\phi$ 在 $\mathscr{M}$ 中為假。

# D. 語義地：不一致、蘊含與反例

**D1. 定義 1.8** 語義地不一致

對於一個公式集合 $\Gamma$ ，如果不存在任何結構使得 $\Gamma$ 的所有公式被定義且為真，我們就說， $\Gamma$ 是語義地不一致的（semantically inconsistent），符號寫作 $\Gamma\models$ 。否則就說， $\Gamma$ 是語義地一致的。

**D2. 定義 1.9** 語義蘊含關係

(1) 如果不存在任何結構，使得公式 $\phi$ 為假且使得公式集合 $\Gamma$ 中的所有公式為真，我們就說， $\Gamma$ 語義地蘊含 $\phi$ ，符號寫作：$\Gamma \models \phi$。

(2) 承上，如果 $\Gamma$ 是空集合，我們就說， $\phi$ 是一個語義學定理，或說，$\phi$ 是一個恆真句（tautology），符號寫作：$\models \phi$。

**D3.** 顯然，$\Gamma \models \phi$，若且唯若 $\Gamma, \lnot\phi \models$。[^6]

**D4. 定義 1.10** 語義序列（semantic sequents）

$\Gamma\models$、$\Gamma \models \phi$ 與 $\models \phi$ 都是一個語義序列。

**D5. 定義 1.11** 反例

說 $\mathscr{M}$ 是序列 $\Gamma \models \phi$ 的一個反例，若且唯若， $\Gamma$ 中的每個公式在 $\mathscr{M}$ 中為真，並且 $\phi$ 在 $\mathscr{M}$ 為假。

# E. 語義學的一些一般定理

**E1. 定理 1.2** 語義蘊含的諸性質

|定理名|定理描述|
|---|---|
|擴充定理（Extension Theorem）|若 $\Gamma \models \phi$，則 $\Gamma , \Delta \models \phi$。|
|重複定理（Repeition Theorem）|若 $\phi \in \Gamma$ 則 $\Gamma \models \phi$ 。|
|減切定理（Cut Theorem）|若 $\Gamma \models \phi$ 且 $\Gamma , \phi \models \psi$，則 $\Gamma \models \psi$ 。|
|遞移定理（Transitivity Theorem）|若 $\phi\models\psi$ ，且 $\psi\models\theta$ ，則 $\phi\models\theta$。|
|否定定理（Negation Theorem）|$\Gamma\models\lnot\phi$，若且唯若 $\Gamma, \phi\models$。|
|連言定理（Conjunction Theorem）|$\Gamma\models\phi$ 且 $\Gamma\models\psi$，若且唯若 $\Gamma\models(\phi\land\psi)$。|
|選言定理（Disjunction Theorem）|$\Gamma, \phi\models\theta$ 且 $\Gamma, \psi\models\theta$，若且唯若 $\Gamma, (\phi\lor\psi)\models\theta$。|
|導衍定理（Implication Theorem）|若 $\Gamma , \phi \models \psi$ ，則 $\Gamma\models(\phi\to\psi)$ 。|
|等同定理（Equivalence Theorem）|$\Gamma , \phi \models \psi$ 且 $\Gamma , \psi \models \phi$ ，若且唯若 $\Gamma \models (\phi \leftrightarrow \psi)$。若 $\Gamma$ 為空集合，我們稱 $\phi$ 和 $\psi$ 是邏輯等同的（logically equivalent）。[^7]|
|分離定理（Detachment Theorem）|$(\phi\to\psi), \phi\models\psi$。|
|窮舉論證（Argument by Cases）|若 $\Gamma, \phi \models \psi$ 且 $\Gamma, \lnot \phi\models\psi$ ，則 $\Gamma \models \psi$。|

**E2. 定理 1.3** 置換定理（substitution theorem）

若 $\Gamma \models \phi$ ，則，對於所有原子語句 $P$ 和公式 $\psi$，$\Gamma (\psi/P) \models \phi (\psi/P)$ 。 

Note: $\Gamma(\psi/P)$ 意味著將 $\Gamma$ 中每個公式中出現的所有 $P$ 置換為 $\psi$ ， $\phi(\psi/P)$ 意味著將 $\phi$ 中出現的所有 $P$ 置換為 $\psi$ 。

**E3. 定理 1.4-I** 全等定理（Congruence Theorem）

對任一個公式 $\theta$ ，

$$(\phi\leftrightarrow\psi)\models\theta(\phi)\leftrightarrow\theta(\psi/\phi)$$

**E4. 定理 1.4-II** 全等定理

若 $\phi$ 和 $\psi$ 是邏輯等同的，並且 $\Gamma(\phi)\models\theta(\phi)$ ，則 $\Gamma(\psi/\phi)\models\theta(\psi/\phi)$。

**E5. 定理 1.5** 對偶定理（duality theorem）

若 $\phi \models \psi$ ，則 $\psi^* \models \phi^*$ 。

Note: $\psi^* $ 被稱作 $\psi $ 的對偶， $* $ 是一個函數，將公式中所有的 $\lor$ 換成 $\land$ ，並將所有的 $\land$ 換成 $\lor$ ，如此有 $\phi^* = *(\phi)$ 。

**引理**：

對於任意的 $\phi$ ，假定 $\phi$ 只由原子語句 $P_1, P_2, \cdots P_n$ 所構成，則 $\phi^*$ 與 $\lnot\phi(\lnot P_1/P_1 , \cdots , \lnot P_n/P_n)$ 是邏輯等同的。

# NOTES

[^1]: 又稱真值函數子/運算子（truth-functors/operators）。

[^2]: 在波蘭記號系統中，(F2)與(F3)會如此改寫：(P2)如果 $\phi$ 是一個公式，那 $N\phi$ 也是。(P3)如果 $\phi$ 和 $\psi$ 都是公式，那 $(A\phi\psi)$、$(K\phi\psi)$、$(A\phi\psi)$、$(C\phi\psi)$ 也是。

[^3]: 我們通常把 $\top$ 和 $\bot$ 作為額外的主要符號。但在這裡，它們是作為語句字母被加進來， $\top$ 定義為「在真值表上總是為真的語句」，而 $\bot$ 定義為「在真值表上總是為假的語句」。

[^4]: 我以 $=$ 表示公式的同一關係，一種等同關係（equivalance relation）。

[^5]: 在布林代數下，我們將對公式 $\phi$ 的分派以賦值函數加以定義。賦值函數是將公式 $\phi$ 對應到 $\\{ 0, 1 \\}$ 的函數 $v$ ，遞迴地以 $\phi$ 之直接子公式的函數值來定義公式的函數值，直到作為直接子公式的原子語句的真值被 $v$ 初始且任意地給定。我們將這稱作一個布林賦值（Boolean valuation）。如果存在賦值函數使得 $\phi$ 對應到 $1$ ，則我們說 $\phi$ 是可滿足的。

[^6]: $\Gamma, \lnot\phi \models \psi$ 為 $\Gamma\cup \\{ \lnot\phi \\} \models \psi$ 的標準簡寫。同樣地，如果 $\Delta$ 是另一個公式集合，我們用 $\Gamma, \lnot\Delta \models \psi$ 簡寫 $\Gamma\cup \Delta \models \psi$ 。

[^7]: 更嚴謹的定義會是：$\phi$ 邏輯等同於 $\psi$ ，然而並不難看出邏輯等同是一個等同關係。