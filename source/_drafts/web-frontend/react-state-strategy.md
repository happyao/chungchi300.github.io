---
layout: post
title: React state strategy in 25 minutes
category: Web前端
keywords: React
date: 2018-04-28 16:09:02
---

# Before Reading

1.  What you can learn after reading this article?

* Determine whether you should store you state.Global or Or component state itself.

2.  How much time you will use for reading this article? 25 minutes for reading.

# State location

| Type   |        Location        |                      Transfer method | Child Transfer state to parent path           | Adv                                                                           | Example                                               |
| ------ | :--------------------: | -----------------------------------: | --------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------- |
| Global | single source of truth | view->action->single source of truth | view->action->single source of truth ->parent | easy notify another view,more easier to trace & easier to store and reproduce | data list,app mode,state that other view need to know |
| Local  | React component state  |         view->view state->child view | parent pass function to child view to set     | encapsulation                                                                 | fliped,hovered.State that only that view need to know |
