---
layout: post
title: Essentialism - api error message design
category: 程序设计
keywords: null
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article?
    Main Programming design

2.  How much time you will use for reading this article?
    25 minutes

# What is our challenge?

Design error rest api message that satisfied

1.  Operation Status
2.  Operation Message(translation)
3.  Operation error message (translation)

# What is the basic requirement?

1.  Enough branching in the message for provide different translation in different component of app.

# What is the highest requirement?

## Optimize the data transfer efficiencies and DRY

1.  We use http response code as indicator(2xx succeed,4xx error).

2.  Global domain for error message(e.g user is not authorized)

## High readability so that client(or any tester) can fill it without learning

1.  Entity Domain(e.g user) for error message

## Silence enough to developer and user seperately(if you have front line supporter,clientServiceCode is also need)

We structuralized the

    {
      developerMessage:"",
      //Mostly don't need to fill,because usually one api call for one operation,the status code is enough to talk about the message
      message:"",
      errors:{
        //describe the global error
        {
            "domain": "global",
            "field": "_error",
            "message": "fail"
        },
        //field error
        {
            "domain": "entity",
            "field": "theFieldName",
            "message": "wrongFormat"
        }
      }

    }

    E.g sign up
    {
      developerMessage:"validation.fail",
      //the 400 indicate the operation is fail is enough
      message:"",
      errors:{
        //describe the global error
        {
            "domain": "membership.registration",
            "field": "_error",
            "message": "onlyAllowAge65AndMaleToRegister"
        },
        //field error
        {
            "domain": "validation",
            "field": "email",
            "message": "wrongFormat"
        },
        {
            "domain": "validation",
            "field": "avator",
            "message": "wrongSize",
            "minWidth":200,
            "minHeight":200
        }
      }
    }

# Determine something should go to message field or global field error

* If the message only tells something that user can fix,put it global field error.
* If the message only notifies user,put it in message field

# Present error message to user in ui by priority

1.  Field error
2.  Global error field
3.  Message

# Referencing

<http://soabits.blogspot.hk/2013/05/error-handling-considerations-and-best.html>

1.  Google cloud drive api
2.  Github api
