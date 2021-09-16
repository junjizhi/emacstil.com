---
layout: post
title: "Ivy: autocomplete with the current selection"
categories: [til]
comments: true
---

Sometimes the thing we want to edit is similar to the selection. When the name
is long, e.g., a long file name, it is cumbersome to type out the full name. So it is handy to just insert the current selection and continue our edit.

Here comes the answer: `M-i` or `(ivy-insert-current)`.

It does exactly what we want: Inserts the current candidate in the minibuffer and continue edit.

Source: [Ivy documentation](https://oremacs.com/swiper/#key-bindings-that-alter-the-minibuffer-input).

Other useful commands:

-   `C-'`: Use avy to select an exact candidate
-   `C-m-j`: Enter the current input as is, and don&rsquo;t match any existing thing down below
-   `C-m-y`: Yank the current directory the mini-buffer, which can be helpful
-   `M-w (ivy-kill-ring-save)`: Copies selected candidates to the kill ring.

