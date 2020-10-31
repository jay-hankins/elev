---
title:  "Quickly Switch GitHub Remote Protocol"
date: '2017-01-01T22:40:32.169Z'
description: Use this bash function to quickly switch between SSH and HTTPS for your GitHub repo remotes.
layout: post
draft: true
---

Happy New Year, everyone. I'll keep it short today. I wrote a little shell function to help me switch my GitHub repo remote URLs between protocols. As you know, GitHub has two methods of access, HTTPS and SSH. Sometimes you'll clone a repo using one protocol but want to use the other one. This nifty script will handle that for you.

`gist:2381100f5e30d34da928407e40ce3c6a`

You can place the above code into your dotfiles for quick use. I have mine in .zshrc. Then, simply run `github_remote_switch` inside your git repo folder, and the script will switch the protocol around for you.

No warranty, but it was tested working on zsh on macOS 10.12. It's basic bash so it should be portable across UNIX-like systems.

Let me know how it works out for you!
