---
layout: post
title: DFT从理论到实践（一）
description: "1.什么是密度泛函理论(DFT)"
modified: 2013-05-31
category: articles
tags: [学术(DFT)]
image:
  local:
  feature: http://ww1.sinaimg.cn/mw1024/4783cef2tw1ec2wm1s2kxj211y0lcgn2.jpg
  credit: Michael Rose
  creditlink: http://mademistakes.com
comments: true  
math: ture

---

# 什么是密度泛函理论(DFT)

在我们开始学术味十足的定义什么是密度泛函理论之前, 我们首先来举几个例子, 来看看密度泛函理论在不同的科学领域中师如何被应用的. 这些精挑细选的例子, 是为了体现出DFT理论在不同的领域中做出的巨大贡献. 

### 1. 混合催化法合成氨
我们举的第一个例子是一个在工业生产中极其重要的一个过程:催化合成氨气 ($$NH_3$$), 作为农业化肥中的主要成分氨, 每年都会生产上亿吨的氨被合成商用. 据估计, 每年全世界有$$1\%$$的能源被用于合成氨. 合成氨的核心公式也非常的简单:
<div>
$$
N_2+3H_2 \rightarrow 2NH_3.
$$
</div>
然而, 要使反应进行,需要高温($$>300^\circ C$$), 高压($$>100\ atm$$), 且存在金属(例如Fe,Ru)作为催化剂. 尽管这些金属催化剂早在100多年前就已经被人们使用, 但是在催化剂表面具体发生了哪些作用, 人们还知之甚少. 造成这种情况的主要原因之一就是催化剂的复杂的结构. 为了让...