---
layout: post
title: 'aide.el - An OpenAI Wrapper on Emacs'
date: '2021-12-27 23:40:18 -0500'
categories: [til]
comments: true
---

Recently I stumbled upon [pen.el](https://github.com/semiosis/pen.el) which interacts with language models, like OpenAI GTP-3. 

This is interesting. Loosely thinking, language models are good complement to Emacs as both are operating on plain text.

I tried pen.el on a Docker container, but it didn't work out of box at my first try.

Also, I look at the [OpenAI API documentation](https://beta.openai.com/docs/api-reference/introduction) and it doesn't seem hard to build a wrapper around it.

After a weekend's work, here is the first implementation of [aide.el](https://github.com/junjizhi/aide.el). 

  > Fun fact: The repo name __aide__ is generated by [OpenAI Product Name Generator](https://beta.openai.com/examples/default-product-name-gen), which reads like AI + IDE, or AI Dwells (in) Emacs :P
  
Think of aide.el as a thin wrapper around APIs like OpenAI.

Currently `aide.el` implementation is minimal: You select a region of text in Emacs, run `M-x aide-openai-completion`, and Emacs shows how AI responds to it.

  
[Try it out](https://github.com/junjizhi/aide.el) and let me know what you think!

-- 

__Edit__: See [the new post](https://emacstil.com/til/2021/12/30/aideel-updates/) for a demo gif.
