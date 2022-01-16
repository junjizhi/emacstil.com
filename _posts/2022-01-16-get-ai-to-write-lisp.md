---
layout: post
title: 'Idea: Get AI to write lisp!'
date: '2022-01-16 10:24:34 -0500'
categories: [til]
comments: true
---
After [playing](https://emacstil.com/til/2021/12/30/aideel-updates/) OpenAI and writing some elisp at the same time, I come up with
this crazy idea: __We can \"outsource\" the mechanical part of
function/macro writing to AI__. 

We have seen how accurate [Github
Copilot](https://copilot.github.com/) helps autocomplete code in VSCode.

The interesting bit about lisp is that, it has powerful macros, which allows
defining DSLs easily and create new programming languages. On the other hand, AI knows all
programming paradigms as well as natural language texts.

Given a task, 1) we can define a function skeleton and get AI
autocomplete a bunch of mundane functions, or 2) generate a list of
steps in natural language, map them to lisp code (the structure should
be close to natural language), and then AI writes macros & functions to
\"implement\" that language!

The 2) idea is more interesting because AI is trained from existing code
corpus. In a sense, we are crowd-sourcing the DSL generation with the
help of AI.

Of course, I\'m not an expert in AI or programming languages, and I have not yet tried to implement it. so take the
idea with a grain of salt. 

Thoughts? Feel free to leave me a comment.
