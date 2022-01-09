---
title:  "Using rlwrap to Improve sqlplus"
date: "2016-09-06T22:40:32.169Z"
description: Make sqlplus less frustrating.
layout: post
---

My friend [Matt Ess](https://matthewess.xyz) helped me configure the [rlwrap](https://github.com/hanslub42/rlwrap) wrapper utility to make `sqlplus` less frustrating to use. I wanted to document the process for anyone else who wants sane keyboard editing inside `sqlplus`.

---

## The Problem with `sqlplus`
Out of the box, `sqlplus` is quite frustrating to use because it doesn't have line editor functionality. This means that if you use your up and down arrow keys, for instance, you do not go through your input history (as in a terminal), but instead you see the escape character for the up/down arrows: `^[[A^[[B` Frustrating!

## The Solution: rlwrap
[rlwrap](https://github.com/hanslub42/rlwrap) is a 'readline wrapper', which allows for the editing of keyboard input for any command. It's quite simple to build and use.

1. Clone the project to your home directory.

   ```
   cd ~
   git clone https://github.com/hanslub42/rlwrap.git
   ```

2. Configure and build the project.

   ```
   cd rlwrap
   autoreconf --install
   ./configure --prefix=$HOME
   make install
   ```

3. Use `rlwrap` to run `sqlplus`.

   ```
   rlwrap sqlplus
   ```

---

Now you've got better keyboard support for interacting with `sqlplus`! Hopefully this makes working with it a little less frustrating (sorry, I haven't found a way to make SQL itself more enjoyable).

Again, shout out to my friend [Matt](https://matthewess.xyz) for the awesome tip.
