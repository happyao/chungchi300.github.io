---
layout: post
title: How to select proper cloud platform for java or php application
category: 程序设计
keywords: http://jeff-chung.com/blog_accessary/blog_images/cloud/cloud-computing.jpg
date: 2018-04-28 16:09:02
---

![ ](http://jeff-chung.com/blog_accessary/blog_images/cloud/cloud-computing.jpg)

For an web application,it is very common to put them to cloud platform for scalability and cost(cash flow) reason.
This article will talk about
1.The advantage and disadvantage of cloud platform(Google app engine,Google compute engine,elastic beanstalk) for you java/php application.
2.Basic suggestion for IT team(manager and software engineer) that is new to cloud platform.

##JAVA on GAE,GCE,EB
###GAE for java
GAE is compatible with spring,spring mvc,struts but you need to do many configuration/modification to it because the GAE support are now supporting servlet2.5 only.
The big table will be the best cost-effective option for your persistence layer.
Moreover,some library will not be feasible for security reason.You cannot write on GAE so that
Best java application to run on GAE is some application that is application built from scratch,very high traffic(GAE and bigtable is very cheap).

###GCE for java
GCE is a IAAS.All java application will be run smoothly on it.The only drawback is relative expensive to elastic beanstalk and it is accessible in Mainland China.

###EB for java
EB is a PASS/IAAS mixture.All java application will be run smoothly on it.The deployment will be automatic after some configuration.
The best java application for EB is deployed frequently and mature framework(For example spring,spring boot).

##PHP on GAE,GCE,EB
###GAE for php
Don't bother to run any framework on GAE,the maturity of php on GAE is very low.

###GCE for php
GCE is a IAAS.All php application will be run smoothly on it.The only drawback is relative expensive to elastic beanstalk.

###EB for php
EB is a PASS/IAAS mixture.All php application will be run smoothly on it.The deployment will be automatic after some configuration.
The best php application for EB is deployed frequently.I have many successful experience on it.For example,laravel framework,wordpress and drupal.

##Basic suggestion for IT manager for cloud platform

1.  Start small,just pick a small project to test on cloud platform first.
2.  Always has a fallback plan.If deployment on one cloud platform don't work well,go to another platform or even traditional deployment.
3.  Frequent deployment.The first deployment should be within first week development to evaluate whether the cloud platform is suitable for the web application.
4.  Make a good balance of development cost and maintenance cost.A low maintenance cloud platform that require high development cost is not worth it.

##Basic suggestion for software engineer for cloud platform

1.  Understand it is necessary to express out your concern and your problem so that the manager can understand the cost.
2.  Start small,just run another sample project of different cloud platform first.
