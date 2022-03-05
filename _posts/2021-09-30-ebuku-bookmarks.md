---
layout: post
title: "Manage Web Bookmarks with Emacs + buku"
categories: [til]
comments: true
---

[buku](https://github.com/jarun/buku) CLI bookmark manager. For those of you who don't want to store bookmarks data in Chrome or Firebox, buku is an alternative.

It comes with an Emacs major mode: [ebuku](https://github.com/flexibeast/ebuku)!

Type `M-x ebuku` you get:

<img width="666" alt="image" src="https://user-images.githubusercontent.com/2715151/135387096-d11c26ea-773f-407d-86d4-f67a5554b908.png">

Then you can search(`s`), open(`RET`), edit(`e`), etc. with Emacs interface.

_Note: For copying URLs, ebuku doesn't have support yet. I have opened a [PR](https://github.com/flexibeast/ebuku/pull/19/files). Meanwhile you can copy the `(ebuku-copy-url)` function to your config and try it out locally_.

__Edits on 2022-03-05__:

I didn't end up using buku a lot after writing this post, mainly I still use
Firefox for my main browser and its bookmarks are good enough for me. 

Also, I blogged about [setting up
pocket-reader.el](https://emacstil.com/til/2022/02/06/pocket-reader-on-emacs/)
to read my bookmarked articles. That's the setup that I currently use.
