---
layout: post
title: 'Doom Emacs Workspace Workflow '
date: '2021-12-02 08:53:46 -0500'
categories: [til]
comments: true
---
The most useful keybinding is `C-c w w`, or `(+workspace/switch-to)`.

This command prompts you a list of workspaces to choose from. I use Ivy for autocompletion, so I can type any workspace name. If there is a match, it goes to the workspace. Otherwise it creates a new workspace with the name. 

Another useful commands is `C-c w d`, or `(+workspace/display)` which lists the existing workspaces. But I use it less often than `C-c w w` because it can show the same list with autocompletion.

Finally, you can set up Doom to [show workspace name in
modeline](https://github.com/hlissner/doom-emacs/issues/314).

_Note: You need to enable [Doom ui:workspaces](https://github.com/hlissner/doom-emacs/blob/develop/modules/ui/workspaces/README.org) to get the above working_.
