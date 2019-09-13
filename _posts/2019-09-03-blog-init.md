---
layout: post
mathjax: true
title: Fan opened his blog
date:   2019-09-03
desc: Fan is very pleased to open his personal blog page
keywords: 'Jalpc,Jekyll,gh-pages,website,blog,easy'
categories:
  - HTML
tags:
  - Jalpc
  - Jekyll
icon: icon-html
published: true
---

This is a raw snippet:

```
hello world
123
This is a text snippet
```

This is a Python snippet:

```
def say_hello():
    print("hello world!")

say_hello()   // "hello world!"
```

Test latex:

 {% raw %}
  $$a^2 + b^2 = c^2$$ --> note that all equations between these tags will not need escaping! 
 {% endraw %}

---

Side note comment: applied a bug fix similar to [this commit](https://github.com/Atlas7/atlas7.github.io/commit/6659f4a47f6ec66987adb0f683a9c6f3842252ae#diff-818954a41dbfb01af70050a459c603b9) to ensure code snippet does not collapse unexpectly upon clicking on it. This issue is tracked [here](https://github.com/jarrekk/Jalpc/issues/97).
