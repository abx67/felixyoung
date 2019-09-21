---
published: true
layout: post
mathjax: true
date: 2019-09-20T00:00:00.000Z
desc: Understanding 2D Dilated Convolution
categories:
  - Learning
tags: null
icon: icon-html
---
From this paper. “[Multi-Scale Context Aggregation by Dilated Convolutions](https://arxiv.org/abs/1511.07122)”, I was introduced to Dilated Convolution Operation.

### Difference between Convolution and Dilated Convolution

Let $F : \mathbb{Z}^2 \rightarrow \mathbb{R}$ be a discrete function. Let $\Omega_r = [-r,r]^2 \cap \mathbb{Z}^2$ and let $k : \Omega_r \rightarrow \mathbb{R}$ be a discrete filter of size $(2r+1)^2$. The discrete convolution operator $\star$ can be defined as

$$(F\star k)(p) = \sum_{s+t=p}F(s)k(t). \tag{1}$$
To generalize this operator, let  be a dilation factor and let  be defined as

$$(F\star_l k)(p) = \sum_{s+l_t=p}F(s)k(t). \tag{2}$$
From formula $(1)$, it is a general definition of convolution, while the kernel size is $p$. For example, let $p=(3,3)$ and $s=(1,2)$ then we get $t=(2,1)$ in order to let $s + t = p$. Then use mapping $F$ to get raw image data and mapping $k$ to get filter data value and conduct simple real number multiplication. Finally sum them up. This is a basic convolution operation.

As for dilation convolution defined as formula $(1). Take the same example as above, let $p=(3,3)$ and $s=(1,2)$ then we get $l_t=(2,1)$ in order to let $s + l_t = p$. And we can e.g. set $t = (4,2)$ which shows in plot $(b). In other word, instead of choose value adjacently from a $(3,3)$ filter, we use a $(7,7)$ filter but only use 3x3 values inside it to conduct convolution operation, which is the red point in plot $(b)$.

### Advantages

By doing this, the receptive field increased from $(3,3)$ to $(7,7)$. Different from pooling, dilated convolution do not lose information, and the meantime increase the receptive field. Every filter output is able to cover a wide range of information.

Dilated convolution is widely and efficiently used in semantic segmentation area.

<img src="../img/_posts/201909/2D Dilated Convolution.png" alt="hi" class="inline"/>
