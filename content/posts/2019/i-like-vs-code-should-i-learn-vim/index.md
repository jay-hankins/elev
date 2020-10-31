---
title: '"I like VS Code. Should I Learn Vim?"'
date: '2019-01-27T21:56:00.007Z'
layout: post
---

Sindre Sorhus maintains an [ama repo](https://github.com/sindresorhus/ama/) where someone asked him [this](https://github.com/sindresorhus/ama/issues/568) question:

> I know some people (even the young ones) still swear by Vim. I am not sure if its worth knowing vim as well?

I took a minute to write some thoughts on Vim and shaking off the daunting
"learn Vim" feeling in a reply to the poster. Spoiler alert, I think it's worth knowing Vim.

---

Hey[ @anishmittal2020](https://github.com/anishmittal2020), I am 23 and just graduated with a computer science degree in May 2018, so I don’t know if you consider me one of the “young ones”, but here are some thoughts. I personally use VS Code around 80% of the time, and Vim 20% of the time. Here’s why I think Vim is valuable:

## Vim is great for remote editing

Over time, you’ll find yourself in situations where using a GUI editor, such as VS Code or Sublime Text, isn’t easy, feasible, and/or possible. For instance, working on remote machines via SSH. Sure, in some cases you can use SFTP or SCP or rsync or whatever to use VS Code to edit remotely, but that’s a lot of work if you’re just trying to make simple changes.

For example, what if you need to quickly change a system’s `hosts` file? If you know Vim, then you just SSH to the system and run `vim /etc/hosts`, save your changes, and you’re done. Again, you could sync directories or even use something like `sshfs` for remote mounts, but that’s a heavyweight solution. Additionally, you may find that due to security concerns you can’t do this direct syncing or mounting.

The same idea expands to Docker containers, where you might want to make a change in-container to verify it before you rebuild the Docker image.

## You don’t have to learn Vim all at once

I think a lot of people get hung up on “learning” Vim because of the jokes about not being able to exit. It’s not just that, obviously, and there is a bit of complexity to Vim. But for all the power it gives you, you can get started with it fairly easily.

- To quit, it’s `:q!`. Just knowing this command, we can learn a few things about Vim: commands start with `:`, can be shortened `quit -> q` and can be forced with `!`.
- To save (write) a file, it’s `:w filename`, which teaches us that we can also give parameters to commands.
- To quit and write, it’s `:wq`, and we learn that commands can be chained together.
  - my friend [Kedar Vaidya](http://kedarv.com) told me that `:x` is essentially a shortcut for `:wq`, meaning it will save then exit. This is cool, so feel free to use it, just don't forget that commands can be chained in Vim 😉
- `hjkl` are the movement keys, along with `w` for “ word” and `b` for “back word”.
- Hit `i` for Insert Mode where you can type. And hit `esc` to get back to the command mode where the keys perform actions rather than typing.

In 5 bullet points, you’ve learned a lot about Vim and know the basics to edit a file. From here you just have to practice by using it, it’s truly the best way to learn something. If you’re familiar with the command line and have gone through the process of learning that, it’s the same thing. You use the terminal as much as you can, figuring out how to do things when you don’t know.

If you didn’t know, there’s `vimtutor` which is a short 30 minute tutorial that helps you learn some more advanced things about vim, like replacement modes, motion, and more. It has you make corrections in place so you practice as you go. I highly recommend it, but again, you don’t have to master everything at once. Vim is flexible, so there’s a lot of stuff you might never use. VS Code is the same way, and I bet you didn’t worry about learning all the ins and outs of it.

## There’s lots of plugins for Vim, it’s harder to curate them

The VS Code extension Marketplace is one of the best parts of VS Code because it makes it easy to find ways to customize the editor to your needs. Vim has mostly the same plugins, in my experience, although it is a bit more challenging to curate and manage them. Mostly you use a plugin manager like `vim-plug` and store configuration in your `.vimrc`.

## VS Code doesn’t run everywhere (yet?\*)

This goes back to the remote editing aspect, but with a twist. I just purchased an iPad Pro for use as an ultra-portable computer when I travel (I really hate lugging laptops in the airport 😅). I rely on SSH and my remote servers to be able to really work (mostly coding and configuration changes). Essentially, the iPad becomes a remote terminal to the server and I’m doing my work there (not unlike the mainframe days 😄) so my only option is an editor that works over SSH. There are lots of editors out there but I prefer Vim!

\* VS Code is just a Javascript application. It’s all just code! ¯\\_(ツ)_/¯ Its editor can and has been shipped in other web apps, so you could potentially find a cloud editor that had similar capabilities (Cloud9? I’m not interested in this because I find the UX of a web editor quite poor, so I don’t really know) today, but that isn’t quite the same. In the future, it’s possible that we’d see VS Code on the iPad or ... VR headsets ... Tesla automobiles? Who knows. Anything is possible. Maybe Vim will come to those platforms too 😎

## Over time, you’ll probably get curious enough to try Vim anyway

This is just what I’ve seen in myself and my peers! 👨‍💻 👩‍💻

You asked if it’s “worth knowing Vim”, and I think the answer is yes, but perhaps you shouldn’t fret about the learning aspect as much as just using it when you can!
