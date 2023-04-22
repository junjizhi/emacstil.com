---
layout: post
title: 'aide.el supports OpenAI Chat API'
date: '2023-04-22 16:57:23 -0400'
categories: [til]
comments: true
---

aide.el now supports calling [OpenAI chat API endpoint](https://platform.openai.com/docs/api-reference/chat), which uses   `gpt-3.5-turbo` model by default. 

I implemented that in the new `aide-openai-chat` function.

You can highlight a region and send it to Chat API and let OpenAI finish the rest. Like previously implemented, Emacs will highlight the response.

Check out the demo:

![2023-04-22 17 08 51](https://user-images.githubusercontent.com/2715151/233806733-7896af09-7f70-4e3b-84d6-ac7bb5c91032.gif)


