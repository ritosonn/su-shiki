---
title: "移送の定義"
date: 2019-04-05T21:33:16+09:00
categories: [ "群論" ]
tags: [ "有限群", "移送" ]
draft: false
---

（有限とは限らない[^1]）群`$G$`とその部分群`$H$`、その正規部分群`$K$`をとり、`$H/K$`が可換になるとする（たとえば交換子群`$K=[H,H]$`など）。このとき、**移送**とよばれる写像`$V\colon G\to H/K$`が定義できるということをみる。[^2]

<!--more-->

[^1]: このサイトではおもに有限群を考えたいので、有限群とは限らない群の話をするときは記事の最初でことわるようにしたい
[^2]: この写像は有限単純群の構造を調べるときに有用である、ということを述べていくつもり

### 定義

`$T\subset G$`を右剰余類に関する完全代表系とする。すなわち
`\[G=\coprod_{t\in T}tH\]`
と表したとき、各`$x\in G,t\in T$`に対して（`$xt\in t'H$`となる`$t'$`が一意に存在するので）ある`$t'\in T,h\in H$`が一意に存在して`$xt=t'h$`が成り立つ。この対応を`$f_x^T(t)=t',h_x^T(t)=h$`と書くことにして、`$V\colon G\to H/K$`を
`\[V(x):=\prod_{t\in T} h_x^T(t)K\]`
で定める（`$H/K$`はアーベル群なので、この定義は右辺の積の順番には依らない）。このとき次の命題を示したい。

命題1：この写像は`$T$`に依らずに定まる準同型である。

### `$f_x^T, h_x^T$`の性質

この記事ではまず`$f_x^T, h_x^T$`が満たす関係式を求める。

補題2：`$f_x^T\colon T\to T$`はT上の置換である。

証明：（単射性）`$f_x^T(t_1)=f_x^T(t_2)$`とすると、

`\begin{align*}xt_1&=f_x^T(t_1)h_x^T(t_1)\\&=f_x^T(t_2)h_x^T(t_1)\\&=f_x^T(t_2)h_x^T(t_2)h_x^T(t_2)^{-1}h_x^T(t_1)\\&=xt_2h_x^T(t_2)^{−1}h_x^T(t_1)\end{align*}`

なので`$t_1=t_2h′$`（ただし`$h′=hTx(t2)−1hTx(t1)\in H$`）である。`$t1,t2$`はHの右剰余類の完全代表系なので、`$t1=t2$`である。

（全射性）任意の`$t′\in T$`に対して、`$t:=x^{−1}t′$`とおけば、`$xt=t′=t′1\in t′H$`なので`$f_x^T(t)=t′$`である。［補題2の証明終わり］

補題3：`$f_{xy}^T(t)=f_x^T(f_y^T(t)),h_{xy}^T(t)=h_x^T(f_y^T(t))h_y^T(t)$`が成り立つ。

証明：定義から`$f_x^T(f_y^T(t))h_x^T(f_y^T(t))h_y^T(t)=xf_y^T(t)h_y^T(t)=xyt$`となるが、このように書き表す方法が一意的だったので主張が従う。［補題3の証明終わり］

補題4：`$S,T\subset G$`を右剰余類に関する完全代表系として、`$\varphi\colon T\to S$`を「同じ剰余類の代表元に移す写像」（つまり`$\{\varphi(t)\}=S\cap tH$`で定まる写像）とし、`$h\colon T\to H$`を`$\varphi(t)=th(t)$`で定めると、`$h_x^S(\varphi(t))=h(f_x^T(t))^{-1}h_x^T(t)h(t)$`が成り立つ。

証明：まず次の等式が成り立つ。

`\begin{align*}x\varphi(t)&=xth(t)\\&=f_x^T(t)h_x^T(t)h(t)\\&=f_x^T(t)h(f_x^T(t))h(f_x^T(t))^{-1}h_x^T(t)h(t)\\&=\varphi(f_x^T(t))h(f_x^T(t))^{-1}h_x^T(t)h(t)\end{align*}`

この式で`$\varphi(f_x^T(t))\in S, h(f_x^T(t))^{-1}h_x^T(t)h(t)\in H$`なので、このように書き表す方法が一意的であることから主張が従う。［補題4の証明終わり］

### 命題1の証明

##### （準同型性）

補題2（`$f_y^T$`は置換）と補題3（`$h_{xy}^T(t)=h_x^T(f_y^T(t))h_y^T(t)$`）を用いると、

`\begin{align*}V(xy)&=\prod_{t\in T}h_{xy}^T(t)K\\&=\prod_{t\in T}h_x^T(f_y^T(t))h_y^T(t)K\\&=\prod_{t\in T}h_x^T(f_y^T(t))K\prod_{t\in T}h_y^T(t)K\\&=\prod_{t\in T}h_x^T(t)K\prod_{t\in T}h_y^T(t)K\\&=V(x)V(y)\end{align*}`

が成り立つ。

##### （`$T$`についてwell-definedであること）

補題2（`$f_y^T$`は置換）と補題4（`$h_x^S(\varphi(t))=h(f_x^T(t))^{-1}h_x^T(t)h(t)$`）を用いると、

`\begin{align*}\prod_{s\in S} h_x^S(s)K&=\prod_{t\in T} h_x^S(\varphi(t))K\\&=\prod_{t\in T} h(f_x^T(t))^{-1}h_x^T(t)h(t)K\\&=\prod_{t\in T} h(f_x^T(t))^{-1}K\prod_{t\in T} h_x^T(t)K\prod_{t\in T} h(t)K\\&=\left(\prod_{t\in T} h(f_x^T(t))K\right)^{-1}\prod_{t\in T} h_x^T(t)K\left(\prod_{t\in T} h(t)K\right)\\&=\prod_{t\in T} h_x^T(t)K\end{align*}`

が成り立つ。

したがって命題1が成り立つ。［命題1の証明終わり］

### 参考文献

この記事は[suzuki]のp522-523から証明を一部補ったものです。

[suzuki]鈴木通夫, 「群論 下」, 現代数学19, 岩波書店, 1978