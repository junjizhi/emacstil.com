---
layout: post
title: 'aide.el Update: Demo and More Commands'
date: '2021-12-30 12:02:52 -0500'
categories: [til]
comments: true
---

I [wrote](https://emacstil.com/til/2021/12/28/playing-with-openai/)  about   a
small OpenAI  wrapper that I developed  over the weekend. After playing with it
for a bit, I extended the functionalities to fit the Emacs workflow.

Now you can `M-x aide-openai-completion-buffer-insert`, which grabs the current
buffer as a string, send it to OpenAI API and insert the result at the end of
the buffer. 

This is like the [OpenAI
playground](https://beta.openai.com/playground) where you can run the command
multiple times to continue the conversation in the same buffer.

Demo:

![aide.ei-demo](https://user-images.githubusercontent.com/2715151/147772615-da36b3ab-a32a-4f7f-b185-e62f3972f8b7.gif)

I also added more
[customization](https://github.com/junjizhi/aide.el/blob/master/aide.el#L31-L59)
that let you control the API parameters. Other helper commands are added as
well. 

Check them out in [Github](https://github.com/junjizhi/aide.el).
