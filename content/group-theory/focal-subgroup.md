---
title: "焦点部分群"
date: 2019-04-07T03:10:42+09:00
categories: [ "群論" ]
tags: [ "移送" ]
draft: false
---

可換群は「移送がべき乗になる群」の例（[参照]({{< ref "group-theory/transfer-example.md" >}})）ですが、そのような移送の作り方として**焦点部分群**で割った剰余群への移送があります。

<!--more-->

---

群`$G$`の部分群`$H$`が与えられたとき、`\[H^\ast=H^\ast_G=\mathrm{Foc}_G(H):=\langle h^{-1}h'\mid h'=h^g, \ h,h'\in H, \ g\in G\rangle\]`を`$H$`の焦点部分群という。

定理1: `$H^\ast\lhd H$`で、`$H/H^\ast$`は可換群である。

証明: 任意の`$h,h'\in H$`に対して`$[h,h']=h^{-1}h'^{-1}hh'=h^{-1}h'^h\in H^\ast$`なので、`$[H,H]<H^\ast$`が成り立つ。「`$K<H<G, K\lhd G, H/K$`が可換ならば`$H\lhd G, G/H$`も可換（[ここ]({{< ref "/group-theory/subgroup-of-subgroup.md">}})の命題7）」なので主張が従う。［定理1の証明終わり］

定理2: `$H^\ast<K<H$`を満たす部分群`$K$`に対して、（`$K\lhd H$`で、`$H/K$`は可換群なので）移送を`$V\colon G\to H/K$`と書くと、任意の`$h\in H$`に対して`$V(h)=h^{[G:H]}K$`が成り立つ。

証明: （方針：移送の定義は`$H<G$`の右剰余類の代表系`$T$`のとりかたによらない（[証明]({{< ref "/group-theory/transfer-definition.md">}})）ので、計算が上手くいくような`$T$`を定義する）

まず、`$x\in \langle h\rangle$`に対して`$(tH)^x:=x^{-1}tH$`とおくと、これは`$\Gamma=\{tH\mid t\in G\}$`上の作用である。[^1]

[^1]:ここでは「群論」（鈴木通夫 著）に倣って右作用なので、左側から積をとると`$-1$`乗がつきます…

この作用の軌道を`$O_1,\ldots,O_s$`と書き、代表元`$t_iH\in O_i$`をとる。すると、`$e_i:=|O_i|$`として`\[O_i=\{t_iH,ht_iH,h^2t_iH,\ldots,h^{e_i-1}t_iH\}\]`であり、`$t_iH=h^{e_i}t_iH$`が成り立つ。つまり`$(h^{e_i})^{t_i}\in H$`である。

これと`$h^{e_i}\in H$`をあわせると、`$(h^{e_i})^{-1}(h^{e_i})^{t_i}\in H^\ast<K$`つまり`$(h^{e_i})^{t_i}K=h^{e_i}K$`（※）が成り立つ。

さて、`$T=\{h^mt_i\mid i=1,2,\ldots,s, \ m=0,1,\ldots,e_i-1\}$`を代表系とする移送を計算したい。

* `$h\cdot h^m t_i=h^{m+1}t_i\cdot 1$`（`$m=0,1,\ldots,e_i-2$`）
* `$h\cdot h^{e_i-1}t_i=h^{e_i}t_i=t_i(h^{e_i})^{t_i}$`

なので、

`\[V(h)=\prod_{i=1}^s\left((h^{e_i})^{t_i}K\cdot \prod_{m=0}^{e_i-2}K\right)=\prod_{i=1}^s (h^{e_i})^{t_i}K\]`

である。ここで（※）より

`\[V(h)=\prod_{i=1}^s h^{e_i}K=h^{\sum_i e_i} K=h^{|G:H|}K\]`

となり、主張が従う。［定理2の証明終わり］

系3: 定理2の状況で、さらに`$|H/K|$`が`$[G:H]$`と互いに素なら、移送`$V\colon G\to H/K$`は全射であり、`$H\cap \ker V=K$`が成り立つ。

証明: `$a[G:H]\equiv 1\pmod{|H/K|}$`なる整数`$a$`をとると、任意の`$hK\in H/K$`に対して`$V(h^a)=h^{a[G:H]}K=hK$`なので`$V\colon G\to H/K$`は全射である。

`$H\supset K,\ \ker V\supset K$`は定義から従う。逆に`$h\in H\cap\ker V$`とすると`$K=V(h)=h^{[G:H]}K$`なので`$h^{[G:H]}\in K$`、よって`$h=h^{a[G:H]}\in K$`である。［系3の証明終わり］