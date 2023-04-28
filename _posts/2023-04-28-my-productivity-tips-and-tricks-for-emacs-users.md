---
layout: post
title: 'Asking ChatGPT about productivity tips for Emacs power users'
date: '2023-04-28 11:37:43 -0400'
categories: [til]
comments: true
---

As a fun experiment, I use [aide.el](https://emacstil.com/til/2021/12/28/playing-with-openai/)  to ask ChatGPT about Emacs productivity tips.

![asking-chatgpt-about-emacs-tips](https://user-images.githubusercontent.com/2715151/235202162-cc8cb7c5-5153-4335-92d6-b211363c4d26.gif)

Here's the text response what I got:

My prompt:

> List five productivity tips and tricks for Emacs power users. Assume these users
can write lisp.

GPT:

> 1. Use org-mode for task management and agenda scheduling, which allows for seamless integration between TODOs, deadlines, and scheduled tasks.
> 2. Utilize keyboard shortcuts for common tasks, such as buffer switching, window splitting, and file saving, to save time and increase efficiency.
> 3. Write custom functions and commands in Emacs Lisp to automate repetitive tasks and workflows, eliminating the need for manual intervention.
> 4. Take advantage of Emacs's built-in version control and git integration to streamline code development and collaboration.
> 5. Optimize Emacs's performance by disabling unnecessary modes and packages, using garbage collection strategies to manage memory usage, and limiting the number of open buffers and windows.

For someone who has been using Emacs for years and [boomeranging back](https://junjizhi.com/all/experience/2021/09/03/back-to-emacs/), these tips are unremarkable. Most of the things I've already known,
   like keyboard shortcuts. For example, use Ctrl + n/p to move up/down one
   line, press Ctrl + a/e to beginning or end of line, meta + f/b to move
   forward/backward one word at time, is something I used ALL the time,
   including in terminals. But likely it is worth emphazing for Emacs newbies.

For the mention of things like org-mode, keyboard macros, and Emacs performance tuning, they are commonly seen and asked in places like Reddit or StackOverflow already, so perhaps ChatGPT aggregates the tips based on popularity.  

For version control, I would point out [Magit](https://magit.vc/), the best git UI for version
   controls. Magit allows you to seamless edit and commit code without leaving
   the editor.

Of course, my prompt is short and not fine tuned at all, so there is room for squeezing more interesting responses from ChatGPT.

__What do you think about these ChatGPT tips?__

Feel free to leave me a comment, or just try  [aide.el](https://emacstil.com/til/2021/12/28/playing-with-openai/) to ask ChatGPT  yourself!
