---
layout: post
title: Use draft-wysiswyg to create power point style multi-text box editor
category: Web前端
keywords: Draftjs
---

## Before Reading

1.  What you can learn after reading this article?

* What is draft js
* Basic components in draftjs and custom style
* What happen when draft js toggle custom inline style
* How draftjs-to-html(a draft js utils library) convert the draftjs to html
* What is draft-wysiswyg
* How draftjs-wysiswyg manage their style
* html to draftjs(draft-wysiswyg only)
* How we combine all these components and build own multi-text box editor?

2.  How much time you will use for reading this article?
    25 minutes for reading.

## What is draft js?

Draft js is a rich-text editor create by facebook.
It has 3 Advantages

1.  Single direction data flow
2.  Build with immutable js
3.  Highly customziable and low customziation cost

## Basic components in draftjs and custom style

[Components in draft js](https://www.lucidchart.com/invitations/accept/a2f3b7ed-ce12-42c9-a452-85bf4908642f)

### Custom style

You can define your own style(and its related css style) and pass to Draftjs(custom style map)

## What happen when draft js toggle one specific custom inline style

If current font not all have the style,their will all have the style.

If current font all have the style,their will all remove the style.

## How draftjs-to-html(a draft js utils library) convert the draftjs to html

It will read the characters and its style and create related 1 character html block with related css(defined by the style) .

## What is draft-wysiswyg

A editor which have predefined styles.

## How draftjs-wysiswyg manage their style

### Style in draftjs-wysiswyg

For example,it have predefined style rules that map 1 css rule

| Style                  | CSS style(color) |
| :--------------------- | :--------------- |
| color-rgb(255,255,255) | rgb(255,255,255) |
| color-rgb(200,200,200) | rgb(200,200,200) |

| Style                    | CSS style(background-color) |
| :----------------------- | :-------------------------- |
| bgcolor-rgb(255,255,255) | rgb(255,255,255)            |
| bgcolor-rgb(200,200,200) | rgb(200,200,200)            |

### draftjs-utils(a library that manage the style in draftjs-wysiswyg)

As you can see that a style(like color) have a similiar pattern(we call it a **style group**).

If we use the draftjs-utils toggle custom inline style(color)(e.g rgb(200,200,200)).

Possible situation:

1.  If current already have color-rgb(255,255,255)**color style group** .It will remove existing rule and replace with new current style (no more color-rgb(255,255,255) and all is rgb(200,200,200)).

2.  If it is already rgb(200,200,200),it will become no color style.

## html to draftjs(draft-wysiswyg only because it read the html character css style and turn it to own style)

The css style color above is the best example

## How we combine all these components and build own multi-text box editor?

1.  Create a group of texts components.
2.  When db click texts components,we convert them to draftjs-editor using html-to-draft js pluin.
3.  When we done editing,we convert them back to html(using draftjs-to-html)

Possible limitation

You want to defined your own style group.Them you can build your own draft js with custom predefined stylemap and develop your own draftjs-utils and html to draftj.s
