---
layout: post
title: 'Doom Emacs: How to fold code blocks'
date: '2021-11-22 18:47:48 -0500'
categories: [til]
comments: true
---
Doom Emacs has
[editor/fold](https://github.com/hlissner/doom-emacs/blob/develop/modules/editor/fold/README.org)
module which makes folding code simple

Steps:

-   Move cursor to the code block opening
-   `M-x +fold/toggle` or `C-c C-f C-f`

Demo (folding a large hash in `ruby`):

![fold ruby code](https://i.imgur.com/nMMKcPi.png)
