---
layout: post
title: restful api naming convention
category: 程序设计
keywords: null
date: 2018-04-28 16:09:02
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article?

design api in restful style

2.  How much time you will use for reading this article?

10 minutes

# The url and method imply action

Restful is source based api style.

We should get 2 information from **uri and method**

1.  resource(which resource?is it a list?is it a item)
2.  action(what action it is doing)

General template

* resource/action
* resource/{id}/action

if the action is empty,it should be a view action

E.g

* user (GET) (view alist of users)
* user (POST)(create user )
* user/batchDelete (DELETE)(delete a list of users)
* user/1/delete (delete )
* user/1

# The parameter provide information support resource action

E.g

* user?filter[]=ageBiggerThen25 (GET) (view alist of users with ages over 25)
* user (which have user information)(POST)(create user ) ) )
