---
layout: post
title: how-critical-thinking-help-me-make-more-good-program-decision
category: 程序设计
keywords: null
date: 2018-04-28 16:09:02
---

![](https://i.ytimg.com/vi/rJYaJ6_UcDM/maxresdefault.jpg)

# Before Reading(Before Reading)

1.  What you can learn after reading this article?

* What is critical thinking
* what is the advantage&disadvantage of it
* Implementation in real life(discussion with my colleague about REST-API, proper HTTP status code for invalid DELETE)

2.  How much time you will use for reading this article?

25 minutes

# What is Critical Thinking

Critical thinking is a **skill** that we use to **find the fact or make decision** in the **best we can(Or based on information we known)**.

## Ability layer

1.  The ability to ask right related and critical question
2.  Ask Question systematically(In a efficient order)
3.  Ask question actively.

## Altitude layer

1.  Keep the conversation going to allow more question in order to get more information(so **be polite instead of being rude**)
2.  Evidence first
3.  Judge everything.Instead of having your opinion and conclusion first and then find evidence(**We are not politician,we are Software Engineer** ).

# What is the advantage&disadvantage of it

## Advantage

1.  Allow you to use your best to **find the fact or make decision**.
2.  Allow you see and review the **structure and content of your argument**.

## Disadvantage

1.  Energy and time consuming.
2.  Take time to train
3.  It use your best ability only.

## Strategy

In a new area we don't know much we absorb knowledge and decision like **spongy** to **absorb basic knowledge**.When thing become critical and in a hard area.We utilize our **critical thinking skill**

# Implementation in real life(discussion with my colleague about REST-API)

## Background

Tester said that my program have a bug that handle delete a resource incorrectly.It show forbidden but the user is the creator of that resource.

I check and realize the program allow user to delete a resource that is not existed anymore(a cached problem).I think is this a server respond bug that I think it should return 404 instead 403(Not authorized).Then I communicate with backend developer(We named he Miller).He confirmed that it do return 403 but it is the case he never think about before.And we have a further discussion about that,and the discussion like that.

## Conversation

Miller:I think it has some point to return 403,if it return 404,it hints a hacker or unauthorized user know that **resource existed and deleted,that is a information leak**(Evidence).
Me:I see,it surely is a good point that I never think before.Is it our application need so high security that leaking a information about **resource existed and deleted** that make us sacrifice the **Discoverability and Maintainability** of the program.Let me think and research.

## Critical thinking(Content and Architecture)

### What is our question/topic?

Proper HTTP status code for invalid DELETE(When resource not existed) in Restful api when leaking a **information about resource existed and deleted** is **not the critical failure of the program.**

### Category of topic

It is a prescriptive topic instead of descriptive topic when it come to **program design decision**.Our preference in this topic are

* Security
* Discoverability
* Maintainability

### Supporting

#### Evidence

* 404 do allow people to realize the resource not existed anymore.
* 404 do expose a information that resource existed and deleted.
* 403 said request is valid but the user don't have the permission.(it basically said resource existed but you don't have the right to do so )
* 401 said the user is not simply unauthorized and not mention whether the existence of resource.

### Conclusion

For proper HTTP status code for invalid DELETE(When resource not existed)

404 is good when **information about resource existed and deleted** is **not the critical failure of the program.**
401 is good when **information about resource existed and deleted** is **the critical failure of the program.**
403 is misleading when **information about resource existed and deleted** is **not the critical failure of the program.**

### Book and reference

* [asking the right questions a guide to critical thinking](https://www.amazon.com/Asking-Right-Questions-11th-Browne/dp/0321907957)
* https://stackoverflow.com/questions/23486992/rest-api-proper-http-status-code-for-invalid-delete
* https://stackoverflow.com/questions/3547474/correct-http-status-code-when-resource-is-available-but-not-accessible-because-o
