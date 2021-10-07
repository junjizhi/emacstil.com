---
layout: post
title: 'Setting up elfeed for RSS feeds'
date: '2021-10-06 22:01:23 -0400'
categories: [til]
comments: true
---

[elfeed](https://github.com/skeeto/elfeed) is awesome! 

I [blogged](https://junjizhi.com/til/2021/10/07/elfeed-rss/) about how I use elfeed to manage all my RSS feeds and read them in the distractionless Emacs window.

This post is about setting up elfeed. 

In Doom Emacs. You just [enable/uncomment](https://github.com/hlissner/doom-emacs/tree/develop/modules/app/rss) the `rss` app in `init.el`, and configure the RSS sources either with the `(setq elfeed-feeds ...)` directly, or with `+org` and configure in `~/org/elfeed.org` (I preferred the latter).


If you are not in Doom Emacs, follow [elfeed doc](https://github.com/skeeto/elfeed) to set it up. Their README is straight forward.

The usage is simple:

![2021-10-06 21 28 59](https://user-images.githubusercontent.com/2715151/136307315-6442d308-2cdf-4a08-96d7-b86b3f2b8d44.gif)

You can do instant search by pressing the `s` key, read a feed by pressing enter, or mark a feed as read, and press `g` to refresh the list.

One quirk I learned is that, elfeed don't really delete your feed. If you don't want to see them as again, just mark the feed as read, and refresh.

Happy reading!