---
title: Installing subl command in OS X El Capitan
date: 2015-11-12
category: Development
---

In any kind of development, most of the work is repetitive, and without a system in place, it would take ages to complete a project. By following this guideline, in my previous installation of Mac OS X Yosemite, I had the Sublime Text 3 CLI `subl` command working according to [this tutorial](http://olivierlacan.com/posts/launch-sublime-text-3-from-the-command-line/) by [Oliver Lacan](https://twitter.com/olivierlacan). This tutorial assumes the `/usr/local/bin` directory as the load path to place the symbolic link of the `subl` command since it's the default load path in OS X.

After performing a clean install of OS X El Capitan, I ran into a problem when I wanted to enable the Sublime Text 3 CLI. These are the steps I took to make it work.

1. I didn't have the `/user/local/bin` path in my system so I had to create it first by running the following command:
```sudo mkdir -p "/usr/local/bin/"
```
2. To create the symlink in that path:
```
sudo ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl
```
3. Closed and reopen the Terminal and worked as expected:
```subl <directory name>```
