---
layout: post
title: 'Edit Text Everywhere with Emacs'
date: '2021-10-03 20:43:06 -0400'
categories: [til]
comments: true
---

[Doom Emacs](https://github.com/hlissner/doom-emacs) comes with the [emacs-everywhere](https://github.com/hlissner/doom-emacs/blob/develop/modules/app/everywhere/README.org) support.

With it, you can edit text anywhere with Emacs. 

For example, if you are solving [Leetcode](https://leetcode.com/) questions and want to edit the code with the Almighty Emacs:

![emacs-everywhere-demo](https://user-images.githubusercontent.com/2715151/135779609-36cae0dd-30d3-49e5-965f-e039c86798e8.gif)

To enable it, you uncomment the `everywhere` app in your Doom `init.el`.

```
:app

everywhere ; *leave* Emacs!? You must be joking
```

In Mac OS X, to invoke the emacs everywhere, I need to set it up as a service. The way to do that is to use `Automator`, and create a `Quick Action`:

<img width="992" alt="image" src="https://user-images.githubusercontent.com/2715151/135779709-87cb2c6a-cb05-4ebf-a0a4-41bde7e1a558.png">

The bash script:

```bash
/path/to/emacsclient --eval "(emacs-everywhere)"
```

Then I assign the hotkey `⌘ + F9` to the service in Keyboard settings:

<img width="661" alt="image" src="https://user-images.githubusercontent.com/2715151/135779857-1832309e-d3d2-41d4-a82c-d59d5c1d8835.png">

Now whenever I press `Command` + `F9` key in any text area of the browser, 



