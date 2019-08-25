---
title: "図式をつなげたり分けたり"
date: 2019-04-14T23:00:04+09:00
categories: [ "圏論" ]
tags: [ "圏論" ]
draft: false
---

図式の一部の可換性から他の部分の可換性が従うか、についてまとめます。

<!--more-->

### 成り立つ例

圏`$C$`において、次の2つの部分が可換であるとします。

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[->] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.3,-0.3) -- (2.7,-2.7);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$a$};
    \node at (3,0) {$b$};
    \node at (3,-3) {$c$};
    \node at (0,-3) {$d$};
    //circlerightarrowの代替
    \draw[-] (2.1,-1) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (2.1,-1) -- (2.102,-1.005);
  \end{tikzpicture}
</script>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[->] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$a$};
    \node at (3,0) {$b$};
    \node at (3,-3) {$c$};
    \node at (0,-3) {$d$};
    //circlerightarrowの代替
    \draw[-] (1.65,-1.5) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (1.65,-1.5) -- (1.652,-1.505);
  \end{tikzpicture}
</script>
</div>

このとき、次の部分も可換になります。

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[->] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.3,-0.3) -- (2.7,-2.7);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$a$};
    \node at (3,0) {$b$};
    \node at (3,-3) {$c$};
    \node at (0,-3) {$d$};
    //circlerightarrowの代替
    \draw[-] (1.1,-2) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (1.1,-2) -- (1.102,-2.005);
  \end{tikzpicture}
</script>
</div>

実際、上の二つの図式を用いて`$(a\rightarrow d) = (a\rightarrow b\rightarrow c\rightarrow d) = (a\rightarrow c\rightarrow d)$`と書き換えることができます。

### 成り立たない例

このような、「外側と、内側の片方が可換ならもう片方も可換」という形の命題が、他にも成り立つか考えてみます。

まずは、上の命題の逆パターンですが、これは次のような例外があります。圏`$\mathbf{Set}$`で、次の図式を考えます。

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[->] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.4,-0.4) -- (2.6,-2.6);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$\{0,1\}$};
    \node at (3,0) {$\{0\}$};
    \node at (3,-3) {$\{0,1\}$};
    \node at (0,-3) {$\{0\}$};
    \node at (1.5,0.3) {$0$};
    \node at (1.75,-1.25) {id};
    \node at (3.2,-1.5) {$\iota$};
    \node at (1.5,-3.3) {$0$};
    \node at (-0.3,-1.5) {$0$};
    //circlerightarrowの代替
    \draw[-] (1.1,-2) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (1.1,-2) -- (1.102,-2.005);
  \end{tikzpicture}
</script>
</div>

（`$\text{id}$`は恒等写像、`$\iota$`は埋め込み（`$\iota(x)=x$`）、`$0$`はゼロ写像（`$0(x)=0$`）のことです）

すると、外側の四角形と左下の三角形は可換ですが、右上の三角形は可換ではありません。

他には、射の向きを一部変えて、次の図式上でも同じような命題が考えられます。

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[<-] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.3,-0.3) -- (2.7,-2.7);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$a$};
    \node at (3,0) {$b$};
    \node at (3,-3) {$c$};
    \node at (0,-3) {$d$};
    //circlerightarrowの代替
    \draw[-] (2.1,-1) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (2.1,-1) -- (2.102,-1.005);
    \draw[-] (1.1,-2) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (1.1,-2) -- (1.102,-2.005);
  \end{tikzpicture}
</script>
</div>

これについては、左下、右上どちらかの図式の可換性からもう片方を導くことはできません。

「外側+左下⇒右上」の反例はこちら：

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[<-] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.4,-0.4) -- (2.6,-2.6);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$\{0,1\}$};
    \node at (3,0) {$\{0,1\}$};
    \node at (3,-3) {$\{0,1\}$};
    \node at (0,-3) {$\{0\}$};
    \node at (1.5,0.3) {id};
    \node at (1.75,-1.25) {id};
    \node at (3.2,-1.5) {$0$};
    \node at (1.5,-3.3) {$0$};
    \node at (-0.3,-1.5) {$0$};
    //circlerightarrowの代替
    \draw[-] (1.1,-2) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (1.1,-2) -- (1.102,-2.005);
  \end{tikzpicture}
</script>
</div>

「外側+右上⇒左下」の反例はこちら：

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[<-] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.4,-0.4) -- (2.6,-2.6);
    \draw[<-] (0.5,-3) -- (2.5,-3);
    \draw[->] (0,-0.5) -- (0,-2.5);
    \node at (0,0) {$\{0,1\}$};
    \node at (3,0) {$\{0\}$};
    \node at (3,-3) {$\{0,1\}$};
    \node at (0,-3) {$\{0,1\}$};
    \node at (1.5,0.3) {$\iota$};
    \node at (1.25,-1.75) {id};
    \node at (3.2,-1.5) {$\iota$};
    \node at (1.5,-3.3) {$0$};
    \node at (-0.3,-1.5) {id};
    //circlerightarrowの代替
    \draw[-] (2.1,-1) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (2.1,-1) -- (2.102,-1.005);
  \end{tikzpicture}
</script>
</div>

### 結論

特殊な場合でこのタイプの命題が成り立ってしまうことはあるかもしれません[^1]が、基本的には「見えている三角形（あるいは四角形、五角形、など）それぞれについて可換性を確かめる」という方法でしか図式の可換性は確かめられない、と考えておくのがよさそうです。

[^1]:そのような例があるかについて自分は知りません。見つけた方はご連絡ください。