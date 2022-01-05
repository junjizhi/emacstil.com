---
layout: post
title: 'Elisp: What does backquote ` do?'
date: '2022-01-05 08:35:17 -0500'
categories: [til]
comments: true
---
Backquote allows you to:

-   quote a list, and
-   selectively evaluate elements of the list (with comma `,`), or:
-   `splice` (eval & spread) the element with `,@`

# Examples

Eval:

```lisp

`(a list of ,(+ 2 3) elements)
;;     ⇒ (a list of 5 elements)
```

Spread:

```lisp
(setq some-list '(2 3))
;;     ⇒ (2 3)

`(1 ,@some-list 4 ,@some-list)
;;     ⇒ (1 2 3 4 2 3)

```
