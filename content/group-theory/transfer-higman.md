---
title: "Higmanの定理"
date: 2019-04-22T23:27:07+09:00
categories: ["群論"]
tags: ["有限群","移送"]
draft: false
---

Higmanの定理を示します。

<!--more-->

---

定理1(Higman): 群`$G$`のSylow `$p$`-部分群を`$P$`とすると、`$P$`の焦点部分群`$P^\ast$`は`$P\cap [G,G]$`に等しい。

証明: `$P^\ast\subset P\cap [G,G]$`は定義から従うので、逆を示す。

`$P$`がSylow `$p$`-部分群なので`$[G:P]$`は`$p$`と互いに素、`$P/P^\ast$`は`$p$`-群なので、[焦点部分群の諸性質]({{< ref "group-theory/focal-subgroup.md" >}}) 系3から、`$P\cap \ker V=P^\ast$`が成り立つ（`$V\colon G\to P/P^\ast$`は移送）。

同じく[焦点部分群の諸性質]({{< ref "group-theory/focal-subgroup.md" >}}) 系3から、`$V$`は全射なので、`$G/\ker V\cong P/P^\ast$`であり、特に`$G/\ker V$`は可換群になる（[焦点部分群の諸性質]({{< ref "group-theory/focal-subgroup.md" >}}) 定理1）。

交換子群`$[G,G]$`の特徴づけとして「`$G/H$`が可換群であるような最小の正規部分群`$H$`」がある。このことから`$[G,G]\subset \ker V$`つまり`$P\cap [G,G]\subset P\cap \ker V=P^\ast$`が成り立つ。［定理1の証明終わり］

系2: `$P/P^\ast$`は`$G/[G,G]$`のSylow `$p$`-部分群と同型である。

証明: Higmanの定理と準同型定理から`$P/P^\ast=P/(P\cap [G,G])\cong (P[G,G])/[G,G]$`である。さらに、`$G/[G,G]$`の中の`$(P[G,G])/[G,G]$`の指数`$|G:P[G,G]|$`は`$p$`と互いに素なので、`$(P[G,G])/[G,G]$`は`$G/[G,G]$`のSylow `$p$`-部分群である。［系2の証明終わり］

系3: `$G$`の正規部分群`$H$`で、剰余群`$G/H$`が可換`$p$`-群になるような最小の部分群を`$G'(p)$`と書くと、`$P/P^\ast\cong G/G'(p)$`が成り立つ。

証明: `$G/G'(p)$`は`$G/[G,G]$`のSylow `$p$`-部分群と同型（詳細は略）なので、系2から主張が従う。［系3の証明終わり］