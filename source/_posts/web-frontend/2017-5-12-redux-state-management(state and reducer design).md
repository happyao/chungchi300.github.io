---
layout: post
title: Redux state management(state and reducer design )
category: Web前端
keywords: null
---

# State design

## Theory

### What make a function should be reducer?

1.  Can manage a state all by itself with the action input
2.  pure function(not mutating the arguments,returning a complete new object to apply state change)
3.  (previousState,action)=>newState pattern

### Flatten as possible,and when and what we need to do when there is a nested state

[Flat adv](http://stackoverflow.com/questions/38842454/why-should-i-keep-the-state-flat) //TODO

### Typical three category data(which can normal lead to pretty flatten state )

1.  domain
2.  app state
3.  ui state

### Advance combine reducer

reference state as three parameter(not immutable it) //TODO

## Practical

### Verification

After design the state design.It is very important to review with other developer(e.g developer lead)(because it state design is so important which I think it is the most important design in frontend development).

P.S

I remember I hit a performance issue.My principle engineer tell me that I can build a hashmap in order to have in memory cache.It takes me 2 weeks to fix it.It is totally preventable if I verify my design with it which should only use 4 hours.

### Refactoring

### Refactoring of state state skill

[best](redux.js.org/docs/recipes/reducers/RefactoringReducersExample.html) Which apply **flatten**,**domain,app ,ui** seperation skill we mentioned before.

### Common State Component(I will complete them later)

* Special common state->form-redux form

* Special common state->i18n-i18n reducer

* Special common state->userAgent

* Special common state->notifications

* Special common state->domain

* Special common state->routing redux-react router

* Special common state->popup redux-react router
