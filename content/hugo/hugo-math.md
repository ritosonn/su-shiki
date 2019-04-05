---
title: "Hugoで数式"
date: 2019-04-03T23:45:40+09:00
categories: [ "Hugo" ]
tags: [ "Hugo" ]
draft: false
---

[Hugo](https://gohugo.io/)で数式を書くためのメモ。

<!--more-->

（[ここ](https://gohugo.io/content-management/formats/)と[ここ](https://discourse.gohugo.io/t/solved-mathjax-not-working/11627)にあるコードを置いただけですが…）

### 方法

適当な場所に次のスクリプトを設置する。

```html
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
  MathJax.Hub.Config({
  tex2jax: {
    inlineMath: [['$','$'], ['\\(','\\)']],
    displayMath: [['$$','$$'], ['\\[','\\]']],
    processEscapes: true,
    processEnvironments: true,
    skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
    TeX: { equationNumbers: { autoNumber: "AMS" },
         extensions: ["AMSmath.js", "AMSsymbols.js"] }
  }
  });
  MathJax.Hub.Queue(function() {
    // Fix <code> tags after MathJax finishes running. This is a
    // hack to overcome a shortcoming of Markdown. Discussion at
    // https://github.com/mojombo/jekyll/issues/199
    var all = MathJax.Hub.getAllJax(), i;
    for(i = 0; i < all.length; i += 1) {
        all[i].SourceElement().parentNode.className += ' has-jax';
    }
  });

  MathJax.Hub.Config({
  // Autonumbering by mathjax
  TeX: { equationNumbers: { autoNumber: "AMS" } }
  });
</script> 
```

### 記述例

基本的に「ふつうのTeXをバックスラッシュで囲む」だけです。

##### ・inlineMath

```
`$e^{i\theta}=\cos\theta+i\sin\theta$`が成り立つ。
```

`$e^{i\theta}=\cos\theta+i\sin\theta$`が成り立つ。

##### ・displayMath

```
`\[\int_0^1 x^2dx=\frac{1}{3}\]`
```

`\[\int_0^1 x^2dx=\frac{1}{3}\]`