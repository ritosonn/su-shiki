---
title: "移送の例"
date: 2019-04-08T00:29:03+09:00
categories: [ "群論" ]
tags: [ "有限群", "移送", "例" ]
draft: false
---


[移送]({{< ref "group-theory/transfer-definition.md" >}})はその群が「どれくらい可換か」を測る道具の一つとして使うことができます。それをみるために、まずは可換群に対して移送が単にべき乗で計算できることを確認して、可換でないいくつかの群についても移送を計算してみます。

<!--more-->

### 例：可換群における移送

命題1: 可換群`$G$`と`$G$`の指数有限な部分群`$H$`、（右）剰余類に関する完全代表系`$T\subset G$`をとり、`$K=[H,H]=1$`のときの移送`$V\colon G\to H$`の値は、任意の`$x\in G$`に対して

`\[V(x)=x^{[G:H]}\]`

となる。

証明: `$V(x)=\prod_{t\in T}h_x^T(t)$`（移送の定義）と`$\prod_{t\in T}t=\prod_{t\in T}f_x^T(t)$`（[ここ]({{< ref "group-theory/transfer-definition.md" >}})の補題2）の積をとって、

`\begin{align*}V(x)\prod_{t\in T}t&=\prod_{t\in T}h_x^T(t)\prod_{t\in T}f_x^T(t)\\&=\prod_{t\in T}f_x^T(t)h_x^T(t)\\&=\prod_{t\in T}xt\\&=x^{[G:H]}\prod_{t\in T}t\end{align*}`

なので従う。［命題1の証明終］

### 例：対称群における移送

命題2: `$G=S_3, H=A_3, K=[A_3,A_3]=1$`のときの移送`$V\colon S_3\to A_3$`は定数写像`$V(x)=1$`となる。

証明: `$S_3=\langle \sigma,\tau\mid \sigma^3=\tau^2=1, \sigma\tau=\tau\sigma^2\rangle$`に対して、
`$xt=t'h$`なる`$x\in S_3$`と`$t,t'\in T:=\{1,\tau\}$`、`$h\in A_3$`を具体的に計算する。[^1]

[^1]:もっと頭のいい方法があるはずですが、手で試せば十分な数なのでやってしまいます。まあ`$\sigma\tau=\tau\sigma^2$`なのを考えればこの表をつくるまでもなく結果は見えるんですが…

| $x$ | $t$ | $t'$ | $h$ |
|:---:|:---:|:---:|:---:|
| $1$ | $1$ | $1$ | $1$ |
| $1$ | $\tau$ | $\tau$ | $1$ |
| $\sigma$ | $1$ | $1$ | $\sigma$ |
| $\sigma$ | $\tau$ | $\tau$ | $\sigma^2$ |
| $\sigma^2$ | $1$ | $1$ | $\sigma^2$ |
| $\sigma^2$ | $\tau$ | $\tau$ | $\sigma$ |
| $\tau$ | $1$ | $\tau$ | $1$ |
| $\tau$ | $\tau$ | $1$ | $1$ |
| $\tau\sigma$ | $1$ | $\tau$ | $\sigma$ |
| $\tau\sigma$ | $\tau$ | $1$ | $\sigma^2$ |
| $\tau\sigma^2$ | $1$ | $\tau$ | $\sigma^2$ |
| $\tau\sigma^2$ | $\tau$ | $1$ | $\sigma$ |

すると`$h$`の2行ごとの積がすべて`$\sigma^3=1$`であることがわかる。［命題2の証明終］

この場合、`$[G:H]=2$`ですが`$S_3$`には位数3の元があるので、べき乗の形では書けません[^2]。

[^2]:こちらもまた面白くない形ですね…べき乗にも定数にもならない移送の例を見つけた人は教えてください。