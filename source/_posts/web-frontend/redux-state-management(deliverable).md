---
layout: post
title: Redux state management(Deliverable)
category: Web前端
keywords: null
date: 2018-04-28 16:09:02
---

# Before Reading

1.  What you can learn after reading this article? Things you must know in order to achieve good state management after you select redux as your state management tool.
2.  How much time you will use for reading this article? 30 minutes

# We choose redux...now what?

We choose redux as our state management lib in order to have **predictable(which mean high readability and easy to debug) state change** (which is achieved by [Three Principle] <http://redux.js.org/docs/introduction/ThreePrinciples.html).However,it> just the starting point of it.If we want more(**performance,quick development,low learning curve,async**) while keeping the predictability,we need to know more about staff in redux.

# Understand the context,what and when we want beside predictable state?

## Performance

### When we want performance?

Different project require different performance level,we can determine it by two factor.

1.  No of Data
2.  Display&changed simultaneously

**Real life case - Image Manipulation Program**: I write a image Manipulation program which require to display ,changed over 20,000 state objects simultaneously and immediately.It require high performance or else it will be super lag so it **require very high performance**.

**Real life case - Normal shopping cart website** only 300-800 object.Moreover ,state objects need to displayed and update partly so it **require low performance**.

### What is the performance

The state change is very quick.Allow render component (react) to determine and rerender the state that's change efficiently.

### How to achieve good performance

## Quick development

### When we want quick development

The development cost mainly on the complex reducer and async action.Too many Actions.

### What is the quick development

Development and maintenance time :).

### How to achieve quick development

1.  [Good Action Design](<http://jeff-chung.com/2017/05/08/redux-state-management(action-design).html>)

## low learning curve

We want low learning curve all the time **:)** .
