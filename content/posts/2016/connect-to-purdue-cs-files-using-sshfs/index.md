---
title:  "Connect to Purdue CS Files Using SSHFS"
date: '2016-08-29T22:40:32.169Z'
description: Mount a remote directory using SSH.
layout: 'post'
---

Here's a quick tutorial on how I access my Purdue CS files remotely so that I can still use all my preferred local development tools, like Sublime Text and my shell customizations.

---

## Install Required Software on Mac OS X
I assume you already have [Brew][] and [Homebrew Cask][] installed on your Mac.

1. Use cask to install [osxfuse][]:

   ```
   brew cask install osxfuse
   ```
2. Use cask to install `sshfs`:

   ```
   brew cask install sshfs
   ```

## Mount Your Remote Directory
1. Run the following command to mount the directory to your local machine:

   ```
   sshfs <username>@data.cs.purdue.edu:/homes/<username>/ \
   ./desired_mountpoint \
   -o auto_cache,reconnect,defer_permissions,noappledouble
   ```

   For example:

   ```
   sshfs hankinsj@data.cs.purdue.edu:/homes/hankinsj/ \
   ./purdue -o auto_cache,reconnect,defer_permissions,noappledouble
   ```

2. Now change to the directory you mounted in. You should see the remote files in the directory, and you can interact with them just as if they were local files on your Mac.

## Unmount Your Remote Directory
1. Run the `umount` command to unmount the directory:

   ```
   umount ./desired_mountpoint
   ```


   For example:

   ```
   umount ~/purdue
   ```

---

Of course, this works on any system that supports SSH, but the case of connecting to Purdue servers to work on projects from home has been especially convenient during my time as a CS student. I've found it to be a bit flaky depending on your network connectivity, and it rarely resumes the mount from a suspend gracefully. However, it's a really convenient way to access your files remotely while still developing locally.

Are you a Purdue CS student that stumbled upon this? Did it help you? Did something not work? Let me know [@jay_hankins](//twitter.com/jay_hankins)!


[brew]: http://brew.sh/ "Brew Website"
[homebrew cask]: https://caskroom.github.io/ "Homebrew Cask Website"
[osxfuse]: https://osxfuse.github.io/ "FUSE for OS X"
