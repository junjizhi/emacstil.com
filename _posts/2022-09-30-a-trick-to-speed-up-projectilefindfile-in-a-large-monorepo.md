---
layout: post
title: 'A trick to speed up projectile-find-file in a large monorepo'
date: '2022-09-30 22:27:41 -0400'
categories: [til]
comments: true
---

When working on a large monorepo (like a ten-year-old Ruby on Rails app), we can use `projectile-find-file` to go to files but it be _slow_ when the file list is long. 

From [projectile documentation](https://docs.projectile.mx/projectile/configuration.html#alien-indexing), we can set the indexing method to `alien` to speed up the find file command:

```elisp
(setq projectile-indexing-method 'alien)
```

This saves _seconds_ when going to files and makes my action much crispier!
