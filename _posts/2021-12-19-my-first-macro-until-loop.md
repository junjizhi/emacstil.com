---
layout: post
title: '"until" loop - My first macro'
date: '2021-12-19 11:36:53 -0500'
categories: [til]
comments: true
---

Recently I was reading _On Lisp_ by Paul Graham and got interested in using macros in Emacs Lisp. I decided to play with it.

Here's my first macro: a `until` loop:

```elisp
(defmacro until (test &rest body)
  `(while (not ,test)
    ,@body))
```

Think of `until` as a negative `while`. The loop runs until the test becomes true.

To use it:
```elisp
(setq jz/counter 1)
(setq jz/res '())
(until (>= jz/counter 5)
  (setq jz/counter (+ 1 jz/counter))
  (setq jz/res (cons jz/counter jz/res)))

;; jz/res => (5 4 3 2)
```

One note about defining macros: If we want to _splice_ the rest of the lisp statement, we need two things:
  - Add a `&rest` in the macro argument List. It means that there are arbitrary number of statements there, and we _wrap_ them all into `body`. 
  - use _comma-at_, or `,@` to splice the `body`. It is similar to the spread operator `...` in Javascript ES6 that can _unwrap_ an object into another.
  
  
I'm not sure whether this is the most efficient way to define macros. But it definitely kicks off an interesting adventure!