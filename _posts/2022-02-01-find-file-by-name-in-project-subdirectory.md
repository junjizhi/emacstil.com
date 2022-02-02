---
layout: post
title: 'Find files by name in project sub-directory'
date: '2022-02-01 23:54:18 -0500'
categories: [til]
comments: true
---

I [blogged](https://emacstil.com/til/2022/01/30/search-something-in-subdirectory-only/)
about how to search something in a sub-directory in a big Rails code
base.

Another workflow I use often is, I know of a file name I want to jump to
and I also know the file is placed in my current sub-directory.

To jump to that file, I could invoke `projectile-find-file`, but it\'s
slow because of the sheer number of files of the project.

Instead, I could use `projectile-find-file-in-directory`, or `C-c p l`
in Doom Emacs to narrow the file search in a sub-directory. This
commands speeds things up a lot for me.
