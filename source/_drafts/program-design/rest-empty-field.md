---
layout: post
title: 'Rest - Empty fields mapping '
category: 程序设计
keywords: null
date: 2018-04-28 16:09:02
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article? Rest - Empty fields map

2.  How much time you will use for reading this article? 10 minutes

# When fields is empty,what should it represent in json

I decide the empty fields by javascript definition

* Empty array = []
* Empty string = "" #because javascript string is primitive type
* Empty Number = 0 #Because Stringify(new Number()) is 0
* Empty Object = null
* Empty Timestamp = null #because javascript DateTime is an object
