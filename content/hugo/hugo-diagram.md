---
title: "Hugoで図式"
date: 2019-04-06T01:21:39+09:00
categories: [ "Hugo" ]
tags: [ "Hugo" ]
draft: false
---

Hugoを使って図式をリアルタイム描画する方法を検討する。[^1]

<!--more-->

[^1]:もちろん貼り付けて表示はできるので、そうしなくて良い方法が知りたい

### TikZは普通に使える！

まずheaderに次を追記する。

```
<script src="https://tikzwolke.com/v1/tikzwolke.js"></script>
```

そのあと、たとえば次をmarkdown中に書き込むと動く[^2]

[^2]:markdownの最中にhtmlが出てくるので見た目がかなり唐突だが、動くものは動く（webは動けば正義みたいな主観がある）一応Chromeで動作確認をしていますが他は保証していません

```
<script type="text/tikz">
  \begin{tikzpicture}
    \draw (0,0) circle (1in);
  \end{tikzpicture}
</script>
```

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw (0,0) circle (1in);
  \end{tikzpicture}
</script>
</div>

なので頑張れば図式を書ける[^3]

[^3]:そのままtikzcdは書けないっぽい（エラーしたときは何も表示されない）

```
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[->] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.3,-0.3) -- (2.7,-2.7);
    \node at (0,0) {$a$};
    \node at (3,0) {$b$};
    \node at (3,-3) {$c$};
    //circlerightarrowの代替
    \draw[-] (2.1,-1) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (2.1,-1) -- (2.102,-1.005);
  \end{tikzpicture}
</script>
```

<div style="text-align: center;">
<script type="text/tikz">
  \begin{tikzpicture}
    \draw[->] (0.5,0) -- (2.5,0);
    \draw[->] (3,-0.5) -- (3,-2.5);
    \draw[->] (0.3,-0.3) -- (2.7,-2.7);
    \node at (0,0) {$a$};
    \node at (3,0) {$b$};
    \node at (3,-3) {$c$};
    //circlerightarrowの代替
    \draw[-] (2.1,-1) arc [start angle = 0, end angle = 330, radius = 0.15];
    \draw[->] (2.1,-1) -- (2.102,-1.005);
  \end{tikzpicture}
</script>
</div>