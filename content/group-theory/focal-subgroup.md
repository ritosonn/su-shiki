---
title: "焦点部分群"
date: 2019-04-07T03:10:42+09:00
categories: [ "群論" ]
tags: [ "移送" ]
draft: false
---

可換群は「移送がべき乗になる群」の例（[参照]({{< ref "group-theory/transfer-example.md" >}})）ですが、そのような移送の作り方として**焦点部分群**で割った剰余群への移送があります。

<!--more-->

群`$G$`の部分群`$H$`が与えられたとき、`\[H^\ast=H^\ast_G=\mathrm{Foc}_G(H):=\langle h^{-1}h'\mid h'=h^g, \ h,h'\in H, \ g\in G\rangle\]`を`$H$`の焦点部分群という。

定理1: `$H^\ast\lhd H$`で、`$H/H^\ast$`は可換群である。

証明: 任意の`$h,h'\in H$`に対して`$[h,h']=h^{-1}h'^{-1}hh'=h^{-1}h'^h\in H^\ast$`なので、`$[H,H]<H^\ast$`が成り立つ。したがって主張が従う。

定理2: `$H^\ast<K<H$`を満たす部分群`$K$`に対して、（`$K\lhd H$`で、`$H/K$`は可換群なので）移送を`$V\colon G\to H/K$`と書くと、任意の`$h\in H$`に対して`$V(h)=h^{[G:H]}K$`が成り立つ。

（証明はあとで追記します）