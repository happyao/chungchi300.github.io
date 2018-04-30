---
layout: post
title: rest-api-101
category: 程序设计
keywords: null
date: 2018-04-28 16:09:02
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article?

* What is rest api
* what is the advantage of it
* Implementation example in real life(login and auth api )

2.  How much time you will use for reading this article?

25 minutes

# Terms

* App state - state that independent to client,only related to the parameter
* Session state - state that related to the client instance and server instance mapping

  How to determine it is session state ? If switching **server instance** and **client** will make the **state change**.it is a **session state**.

* Idempotent - the **side effect** of calling multiple and calling single once time are **equal**

# What is rest api

* Resource base and method api style on http

* Session state not located in session-(either change to holded by client or app state)

* Request only initialize from client

* Stateless Connection protocol(http)

# What is the advantage of it

1.  Scalability
2.  High Readability
3.  Cache
4.  because sensitive api can be indempotent,don't need to worry calling sensitive api twice
5.  Decoupled client and server

# Implementation example in real life(login and auth api )

## Login API

/login

params:

* username
* password

return:

* Can be token

* Can be cookie(the server instances accessing their cookie must be in a centralized storage like database or redis cluster)( **in order to move the cookie in server instance from session state to application state** )

## User info API

/user/me(a special resource id)

params:

* can be cookie
* can be token

return: user information

P.S

* [Naming convention and method](/2017/04/25/Restful-api-naming-convention,method-and-params.html)

* [Empty Fields](/2017/05/18/rest-empty-field.html)
