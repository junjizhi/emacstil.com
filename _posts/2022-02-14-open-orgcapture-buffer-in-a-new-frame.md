---
layout: post
title: 'Open org-capture buffer in a new frame'
date: '2022-02-14 19:19:34 -0500'
categories: [til]
comments: true
---
By default, org-capture opens a popup buffer at the end of current
window, and allows to type in the content. But I find the current buffer
displays too much info, and I was looking to maximize / full-frame the
org-capture buffer.

Tried a
[few](https://stackoverflow.com/questions/15253005/in-emacs-org-mode-how-do-i-get-org-capture-to-open-in-a-full-sized-window)
[suggestions](https://fuco1.github.io/2017-09-02-Maximize-the-org-capture-buffer.html),
but they didn\'t work.

I found [a different
solution](https://github.com/hlissner/doom-emacs/issues/3614#issuecomment-662679188)
instead: `+org-capture/open-frame`.

And I can customize the frame size:

``` elisp
(setq +org-capture-frame-parameters '((name . "doom-capture")
                                      (width . 170)
                                      (height . 110)
                                      (transient . t)
                                      (menu-bar-lines . 1)))
```

Now org-capture can open in a new frame with the size I want, and
doesn\'t mess with current window setup at all.
