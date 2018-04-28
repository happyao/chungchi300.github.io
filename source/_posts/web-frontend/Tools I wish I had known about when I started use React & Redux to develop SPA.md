---
layout: post
title: Tools I wish I had known about when I started use React & Redux to develop SPA
category: Web前端
keywords: React,Redux
date: 2018-04-28 16:09:02
---

React Dev Tool
Snapshot
Chrome Url

Redux Dev Tool
Snapshot
Chrome Url

Create React App
Snapshot
npm install method

Common SPA Problem you must faced & Solution which I used and proven to work well in React & Redux

Network Call=>redux-thunk + redux-api-middleware (My Github Repo)

## Both

* Common Function => Lodash
* Validation => validator js https://github.com/chriso/validator.js/
* Routing=>react-router-redux
* Multi-language=>react-localize-redux
* Form => Redux Form
* Backend => Admin on Rest

## React:

* Styling=>Styled Components
* SVG(image asset)=>svgr (My link)
* Modal => react-modal https://stackoverflow.com/questions/35623656/how-can-i-display-a-modal-dialog-in-redux-that-performs-asynchronous-actions/35641680#35641680
* Read more https://github.com/brillout/awesome-react-components

## Redux:

* Update deeply nested state in reducer=>immutability-helper
* Device Checking =>mobile-detect

Dig Deeper

## React

http://nayaabkhan.me/react/the-react-philosophy

function(state) = UI(Components)

Power
Modularity
Composition

## Redux-

Single source of truth: The state of your whole application is stored in an object tree within a single store.
State is read-only: The only way to change the state is to emit an action, an object describing what happened.
Changes are made with pure functions: To specify how the state tree is transformed by actions, you write pure reducers.
