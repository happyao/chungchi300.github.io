---
layout: post
title: General-Agile-program-design-process
category: 程序设计
keywords: null
date: 2018-04-28 16:09:02
---

<!-- TOC -->

- [Reading Time](#reading-time)
- [Content](#content)
    - [Purpose of program design](#purpose-of-program-design)
    - [What is a good program design](#what-is-a-good-program-design)
    - [How to do program design in agile development](#how-to-do-program-design-in-agile-development)
    - [When is a good time to use diagram and words to describe program design](#when-is-a-good-time-to-use-diagram-and-words-to-describe-program-design)
        - [Good Signals](#good-signals)
        - [Bad Signals](#bad-signals)
    - [Tools to describe program design(UML & Software to create UML)](#tools-to-describe-program-designuml-software-to-create-uml)
        - [Diagrams](#diagrams)
            - [Random](#random)
            - [UML](#uml)
                - [Static Diagrams:](#static-diagrams)
                - [Dynamic Diagrams:](#dynamic-diagrams)
        - [Text](#text)
- [Thanks:](#thanks)

<!-- /TOC -->

# Reading Time

25 minutes

# Content

## Purpose of program design

Create a **model** of

* Program Components
* How Program Components Interacts with other

to specific **program problem(Requirement)**.

## What is a good program design

Model that **has lowest complexity to human**.

Principle that we use to lowest complexity(I will create one post for each item)

* Reduce General Complexity
* Prefer data complexity then procedure complexity
* Reduce unnnessary Complexity
* Avoid Usage Complexity
* Understand Complexity easily
* Reduce extense complexity

## How to do program design in agile development

In a iteration process of agile development.

We do **small upfront** design(in uml or another draft tool) and **do some implementation** to get **some feedback** to our **design**.The whole process is **iterative** until we get **good feasible program design for this iteration process**.

## When is a good time to use diagram and words to describe program design

Because there is time consumption for create and maintain the **descriptions of program design using diagrams and words**. Therefore we want to keep them **as minimal as possible** . Therefore,**ensure** you have following **purposes** before **drawing and writing**

* Play with **program design ideas**
* To Communicate with other software engineer
  * They want to know the specific part of program design
  * They disagree know the specific part of the program design

### Good Signals

If you find you are frequently re-create a program design and descriptions and get rid of old design. It means you **should do them more**.

### Bad Signals

If you find your program design and descriptions only need **write once and works**. It may well it is **too simple to use diagram and words to describe**.You **should not describe this simple program design**,just keep them **in mind or use program code to describe it is well enough**

## Tools to describe program design(UML & Software to create UML)

### Diagrams

#### Random

You can use random diagram(if the reader is yourself only).

#### UML

If the readers are other developer,it is good to use UML.Here are common diagrams use

##### Static Diagrams:

* Purpose : Description Unchanging Logical Entity of Software
* E.g : Describe class,object,data structure,relationship betweens them
* **Class Diagram**,Object Diagram,ERD diagram

##### Dynamic Diagrams:

* Purpose : Show software entity change during execution
* E.g : Function call,flow of execution,State change
* **Sequence Diagram,State Diagram**

Tools for drawing:PlantUML are the great tool I used to draw UML because

* portable because JAVA based
* easy to draw and maintain because it can create UML Diagrams using simple textual description(very low learning curve)

### Text

Tools for Writing:Markdown are the tool I used because

* easy write and read
* formatting

# Thanks:

* UML for Java Programmers
* Agile software development principles, patterns, and practices
