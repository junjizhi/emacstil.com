---
layout: post
title: 'Hide leading/trailing emphasis markers in Org mode'
date: '2021-11-25 19:18:12 -0500'
categories: [til]
comments: true
---
When you edit org files, sometimes you want to emphasize words like
`code` or `verbatim`. 

By default, Doom Emacs shows the leading or trailing marker characters  like `=` or `~`. So the org file looks funny.

Naturally, you want to hide the these characters, like an `org-link`. 

[This SO answer](https://stackoverflow.com/a/10970665) provides a solution: **Toggle on  `org-hide-emphasis-markers`**

Before:

![before tweaking](https://i.imgur.com/xWEkfqP.png)

After:

![font screenshot](https://i.imgur.com/GPe9rj9.png)

To further customize each emphasis face, you can tweak the
`org-emphasis-alist` variable and pick or customize each face, like `org-verbatim`. [Here is an example](https://mullikine.github.io/posts/org-mode-bold/).
