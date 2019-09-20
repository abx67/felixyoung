---
published: true
layout: post
mathjax: true
date: {}
desc: Understanding 2D Dilated Convolution
categories:
  - Learning
tags: null
icon: icon-html
---

So from this paper. “[Multi-Scale Context Aggregation by Dilated Convolutions](https://arxiv.org/abs/1511.07122)”, I was introduced to Dilated Convolution Operation.

### Difference between Convolution and Dilated Convolution

Let $F : \mathbb{Z}^2 \rightarrow \mathbb{R}$ be a discrete function. Let $\Omega_r = [-r,r]^2 \cap \mathbb{Z}^2$ and let $k : \Omega_r \rightarrow \mathbb{R}$ be a discrete filter of size $(2r+1)^2$. The discrete convolution operator $\star$ can be defined as

(F\star k)(p) = \sum_{s+t=p}F(s)k(t). \tag{1}
To generalize this operator, let  be a dilation factor and let  be defined as

(F\star_l k)(p) = \sum_{s+l_t=p}F(s)k(t). \tag{2}
From formula , it is a general definition of convolution, while the kernel size is . For example, let  and  then we get  in order to let . Then use mapping  to get raw image data and mapping  to get filter data value and conduct simple real number multiplication. Finally sum them up. This is a basic convolution operation.

As for dilation convolution defined as formula . Take the same example as above, let  and  then we get  in order to let . And we can e.g. set  which shows in plot . In other word, instead of choose value adjacently from a  filter, we use a  filter but only use 3x3 values inside it to conduct convolution operation, which is the red point in plot .

Advantages

By doing this, the receptive field increased from to . Different from pooling, dilated convolution do not lose information, and the meantime increase the receptive field. Every filter output is able to cover a wide range of information.

Dilated convolution is widely and efficiently used in semantic segmentation area.

Computer Vision and Machine Learning > Understanding 2D Dilated Convolution > Screenshot from 2019-08-28 16-51-02.png
