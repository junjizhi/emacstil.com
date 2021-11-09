---
layout: post
title: 'Upload and insert hosted images into Org files'
date: '2021-11-09 08:43:45 -0500'
categories: [til]
comments: true
---
Automating image workflows can minimize the friction of
dealing with images. This is useful when you need to insert images or screenshots into your blog articles

## Automate uploading images to the Cloud

I use [uPic](https://github.com/gee1k/uPic). 

> **_NOTE:_** This app is available in Mac OS X only.

You can follow the
[instructions](https://blog.svend.cc/upic/tutorials/github/) to
configure Github as the hosted service. There are other image hosted services too. 

Add a shortcut for taking screenshots and auto uploading to the
service:

![Shortcut for taking sceenshots and uploading
images](https://i.loli.net/2021/11/09/OKtYbLASjcsRWE4.png)

Now pressing `Cmd + F8` allows me to select the screen area to capture.

**When done capturing, it automatically uploads and add the image URL to the clipboard**!

## Insert images into Org files {#insert-images-into-org-files-1}

If you don\'t need to preview the images, the simple solution is just
yank (Ctrl + y) the URL into the org file.

However, if you need to convert Org files into other formats, e.g.,
Markdown, [Pandoc](https://pandoc.org/) has some
[quirks](https://github.com/jgm/pandoc/issues/5454) about dealing with
image URLs.

To setup proper image links, we need to add at least #+CAPTION on top:

    #+CAPTION: label
    [[/path/to/image]]

which leads to my [snippet](https://github.com/joaotavora/yasnippet) to
**automate creating image link from clipboard**:


    # -*- mode: snippet -*-
    # name: Add image link (from clipboard)
    # key: <i
    # --
    #+CAPTION: ${1:Caption}
    [[`(current-kill 0)`]]

## Summary: My workflow

-   Press `Cmd + F8` to take a screenshot and get the image URL in
    clipboard
-   Type `<i` and TAB
-   Enter a caption and TAB
-   Press `C-c TAB` to toggle the image view
