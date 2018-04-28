---
layout: post
title: Same Origin policy and CORS
category: 程序设计
keywords: null
date: 2018-04-28 16:09:02
---

# Before Reading

1.  What you can learn after reading this article?

1.  Same Origin strategy
1.  CORS
1.  jsonp(</2015/10/07/jsonp-tutorial.html>)

1.  How much time you will use for reading this article? 30 minutes

# Flow

## Same origin strategy

![ ](/blog_accessary/blog_images/same-origin-and-cors/same-origin.png) Browser is OS js and origin is application

## Read From CORS

![ ](/blog_accessary/blog_images/same-origin-and-cors/read-request-cors.png) The requested resource is called once and actually returned to OS even if CORS not permitted.But the Browser will not pass data to **JS1**.

## CUD From CORS

![ ](/blog_accessary/blog_images/same-origin-and-cors/cud-request-cors.png) The requested operation will not be called because the browser **read and check the response of preflight request**

**preflight request hints** Both preflight request and actual CUD request need to return same cors response.E.g

Access-Control-Allow-Methods:GET, POST, PUT, DELETE, OPTIONS Access-Control-Allow-Origin:<http://rdv.dpms.com:9966>

# Implementation

## Http Response header for CORS

Allow Origin:<http://abc.com> Allow methods :PUT,GET,POST,OPTIONS(Preflight request)

## Server

1.  Origin 2 need to added those header in http response.
2.  Handle preflight request properly

## Cookie

If cookie is used in request.It cannot be too general.(e.g `*`)
