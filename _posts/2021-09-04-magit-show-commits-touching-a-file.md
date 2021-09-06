---
layout: post
title: "Magit: Show commits touching one file only"
categories: [til]
comments: true
---


It&rsquo;s useful if you want to see file edit history:

-   Open `(magit-status)`
-   press `l`
-   limit to files `--`
-   press `l` again

Tip: You use the regex pattern to match multiple files.

**Alternative**: Use `magit-blame`, or `C-c v B` to see the commits overlay on the file, but if the file is changed often, the information can be too dense to look at. The above trick prints out a list of commits, which is cleaner.

Reference: [StackOverflow](https://stackoverflow.com/a/37530653)

