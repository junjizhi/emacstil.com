---
layout: post
title: 'How to define an interactive function with multiple prompts '
date: '2023-04-27 15:06:31 -0400'
categories: [til]
comments: true
---
Today I tried to define a function that prompts the user for multiple
arguments in a single function call. 

I knew I need to use the `interactive` form. But when I read the  [`interactive`
form documentation](https://www.gnu.org/software/emacs/manual/html_node/elisp/Using-Interactive.html),
it is a bit hard to read without code examples. 

So I tried to tinker with it by trying this function:

``` elisp
(defun test-fn (arg1 arg2)
  (interactive "sEnter arg1: \nsEnter arg2: ")
  (message "arg1: %s, arg2: %s" arg1 arg2))
```

And it works as expected. The trick is to separate the prompts with a newline `\n`.

This way, it defines a function an interactively-callable command that accepts
multiple prompts in one function.


If you are curious about what \"s\" code does, take a look at [this
page](https://www.gnu.org/software/emacs/manual/html_node/elisp/Interactive-Codes.html).
