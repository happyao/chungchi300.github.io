---
layout: post
title: Redux state management(Action design )
category: Web前端
keywords: null
date: 2018-04-28 16:09:02
---

# Action design

## FSA

FSA is just a design style for action.

Adv:

* Human-friendly. FSA actions should be easy to read and write by humans.
* Conventional

  1.  Type->the action name,should able to look at
  2.  Payload->data support the action() <!-- just like rest api -->
  3.  error->true or false,if true,the payload should be a **error object** about the message.
  4.  Meta->extra information that is not in payload.

* Simple. FSA definition is straight forward

* **Last but most important**.Many useful redux library only support FSA action

## PS.Meta usage

In admin on rest ,it use meta to fetch dependent resource
