---
layout: post
title: 'Emacs: Change the case of N words in one go'
date: '2021-12-12 12:33:59 -0500'
categories: [til]
comments: true
---

`digit-argument` + `negative-argument` = Great way to maintain editing tempo.

For example:

-   to capitalize three words forward, you can do `M-3 M-c`.
-   for three words backward, you can apply the negative argument:
    `M-- M-3 M-c`

This way, your hand don\'t need to move away from the `meta` key and
maintain editing tempo.

Note: For Doom Emacs, `M--` is mapped to decrease font size instead,
which I don\'t use often, so I have to switch it back:

``` elisp
(global-set-key (kbd "M--") 'negative-argument)
```
