---
layout: post
title: 'Ivy Find File and Open in a New Window  '
date: '2021-10-05 09:32:04 -0400'
categories: [til]
comments: true
---

Sometimes we find a file but don't want to interrupt the work in progress in the current window. It is best to open it in a new window (or _frame_, in Emacs term).

If you are using [Ivy / Counsel / Swiper](https://oremacs.com/swiper), try the below workflow:

1. `M-x counsel-find-file`, or type `C-x C-f`
2. Fill out the file name with the help of auto-completion (Tip: [Use `M-i` to complete the name without jumping to it](https://emacstil.com/til/2021/09/16/ivy-completion-with-current-selection/))
3. Press the [Hydra key](https://oremacs.com/swiper/#hydra-in-the-minibuffer) `C-o` to open the Hydra menu
4. Press `f` to open in another frame. Voila!

Bonus: There are other actions available in the Hydra menu, like copying the file path, mkdir, deleting file, etc. 

Basically if we want to do any file related action, simply type `C-x C-f` and _wire up the action_ as we need. 

It's neat!

Demo:

![find-file-open-in-new-window](https://user-images.githubusercontent.com/2715151/136033348-815bc396-ec72-4a03-86fd-40a69018f45b.gif)
