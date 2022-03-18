---
layout: post
title: 'AI Paraphrasing on Emacs'
date: '2022-03-17 22:18:17 -0400'
categories: [til]
excerpt: 'I updated aide.el to use the new OpenAI Edits API for paraphrasing text, on Emacs!' 
comments: true
---

If you are like me and do all your writing on Emacs, you probably setup
spelling & grammar checks on Emacs already. Sometimes you want Emacs to
go a step further. What if Emacs can assist writers who need to
paraphrase large text blocks --- like replacing words with synonyms?

A while ago I built
[aide.el](https://emacstil.com/til/2021/12/30/aideel-updates/), a
lightweight elisp wrapper for OpenAI. aide.el could accept a region or
the entire buffer and send it to OpenAI for autocompletion.

However, autocompletion is not really paraphrasing. Even though we could
build the instructions or examples in the prompt to tell AI to
paraphrase it, it does not always work.

Recently OpenAI [announced the new GPT-3
capabilities](https://openai.com/blog/gpt-3-edit-insert/). So I updated
[aide.el](https://emacstil.com/til/2021/12/30/aideel-updates/) to use
the new Edit & Insert APIs (Still in beta, as of writing).

Let\'s see the new function `aide-openai-edits-region-replace` in
action:

![aide.el paraphrase interest rates text with openai on doom emacs](https://user-images.githubusercontent.com/2715151/158926373-0eca9317-7432-483a-9336-ddc39d68c220.gif)

After you select a region of text, invoke the command, and send it to
OpenAI, and replace the region with the result.

With this new function, it should help your text editing and
supercharge your writing!
