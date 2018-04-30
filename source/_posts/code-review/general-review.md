---

title: Code Review 做法和好处
date: 2018-04-30 11:43:00
tags:
category: Code Review
keywords: null
---

{% asset_img measure.jpg %}

# 阅读前

1.  阅读这篇文章后你能学到什么?

Code Review 做法和好处

2.  你将用多少时间来阅读这篇文章?

25 分钟

# 好处

* **分享知识**
* **提高代码的可读性**

# 做法

* 在每次 Code Review 和 解决 bug 之后,我们都會发现新的有效做法并写在 CONTRIBUTION.md 上,共同维护最佳做法
* 定期地 - 每个星期五我们都會做 Code Review

# Code review 做得好和做得不好的信号

## 好

* 团队成员知识增长 Team member knowledge increase
* 团队成员接受培训而不是批评 Team member feel being trained instead of criticized
* 团队成员知道代码评审何时发生并期待它 Team member know when the code review happen and look forward to it
* 给定特定的代码块，您无法判断是谁编写的。Given specific block of code,you cannot tell who write it.
* 相同/相似的 bug 不会重复两次 Same/similar bug don’t repeat twice

## 不好

* 毫无理由地批评代码——当你指出一个代码写得很差时，你不能指出相关的代码 on CONTRIBUTION.md criticize code without reason - When you point an code written poorly,you cannot point that related implementation on CONTRIBUTION.md

# 例子

* {% post_link code-review/general %}

React & Redux

* {% post_link code-review/action %}
* {% post_link code-review/reducer %}
* {% post_link code-review/helper %}
* {% post_link code-review/smart-component %}
* {% post_link code-review/dummy-component %}
* {% post_link code-review/middleware %}
* {% post_link code-review/network %}
* {% post_link code-review/asset %}
