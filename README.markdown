# Gitolite hooks

These are a collection of gitolite hooks used by the
[OSUOSL](http://osuosl.org). Its a handy system that allows you to easily
enable/disable and configure any custom git hooks you need from gitolite.

It utilizes a centralized post-recieve hook that will execute hooks in another
directory that can enabled or disabled via git config. This isn't completely
tied to gitolite itself, however it integrates well.

# Installation

For now this is a manual installation.

1. Clone this repo into /usr/local/share/gitolite-hooks
1. Find where your gitolite installation is at which will generally be in
   /usr/share/gitolite. 
1. Symlink /usr/local/share/gitolite-hooks/common/post-receive to
   /usr/share/gitolite/hooks/post-receive. You may need remove the file that
   already exists.

That's it!

# Usage

To enable a hook:

    config    hooks.enabled   = post-receive-email-infra, github-push

*NOTE: Ensure you use a comma as a separator*

Check each hook for their individual settings.

# TODO

Add configure/makefile for installation and make the paths portable. Right now
everything assumes a specific path.

# Contributing

This is like any open source project. If you want a pony, you can contribute it
via a patch or pull request.

## Copyright (C) 2012 Oregon State University

This work is licensed under a [Apache License, Version
2.0](http://www.apache.org/licenses/LICENSE-2.0.html) (Unless otherwise
licensed).
