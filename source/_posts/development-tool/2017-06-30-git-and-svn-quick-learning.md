---
layout: post
title: Learn Git and Svn in two graph instead of two hundred commands
category: 开发工具
keywords: null
---

# Before Reading(Before Reading)

1.  What you can learn after reading this article?

Learn git & svn in the prospective of data instead of their procedures to get the whole picture

* How much time you will use for reading this article? 25 minutes
  es

## Why we don't learn commands first?

Because we are human,data is much more easier to understand and meaningful then procedures.If we can learn in the data first,we can understand & apply those proper Knowledge to undergo proper operation.

## Git

<div class="center" style="width: 960px; height: 720px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:960px; height:720px" src="https://www.lucidchart.com/documents/embeddedchart/64bbe993-4d80-425a-a0b8-30b3f65408b9" id="7JDb.imKG_hY"></iframe></div>

## Merge && Rebase - different method to merge other people code

### Merging

**Procedures**

1.  Git add -A
2.  Git commit -m"local update"
3.  Git pull(which trigger git checout and Merging)
4.  Git add -A
5.  Git commit -m"merged result"
6.  Git push

**What procedures really do?**

it means merge a group ocommits(files) from local anremote branch into oncommit(files).

### Rebase

1.  Git add -A
2.  Git commit -m"local update"
3.  Git pull --rebase(which trigger git checout and Merging)
4.  Git rebase --continue && Git add -A (multiple times,depends on the number of commit)
5.  Git commit -m"rebased result"
6.  Git push

### Stashing hack(update latest version and apply local file changes)

**Procedures**

1.  Git stash(restore files to original version)
2.  Git pull(which trigger git checout,it will always successful checkout because all files are in last version)
3.  Git stash pop(apply the changes)
4.  Git add -A
5.  Git commit -m"apply changes to latest version"
6.  Git push

**What procedures really do?**

it means merge a group ocommits(files) from local anremote branch into oncommit(files).

## Svn

<div class="center" style="width: 960px; height: 720px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:960px; height:720px" src="https://www.lucidchart.com/documents/embeddedchart/00b25a30-54be-403c-9665-9f286dc1211c" id="GFDbOms4Pgfw"></iframe></div>
