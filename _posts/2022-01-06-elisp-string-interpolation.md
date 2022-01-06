---
layout: post
title: 'Elisp: String interpolation'
date: '2022-01-06 09:12:37 -0500'
categories: [til]
comments: true
---

Use `format` or `concat`:

```lisp
(format "abc %s" "cdf")

(concat "abc " "cdf")
```

`%s` is to be replaced with the printed representation of the object. 

In Emacs lisp, `%` + one char is called _format specification_. 

See the list of other format specification [here](https://www.gnu.org/software/emacs/manual/html_node/elisp/Formatting-Strings.html).
