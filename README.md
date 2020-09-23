# Git Ensure Main

This is an extension to git that ensure one is on the main branch:

```
$ git branch --show-current
main
$ git ensure-main
$ git checkout -b feature-branch
$ git branch --show-current
feature-branch
$ git ensure-main
ERROR: must be on main branch
```

## Install

There are a few ways to get this script added to git, but my favorite is by
adjusting your `$PATH`. But before we can do that, we have to have the script
locally:

```
# you probably have a folder where you clone stuff - go there:
$ cd path/to/code/folder
# clone this project
$ git clone https://github.com/jonallured/git-ensure-main.git
```

Then adjust your $PATH, maybe something like this:

```
# in a file like ~/.zshrc
export PATH=path/to/code/folder/git-ensure-main/bin:${PATH}
```

Then open a new terminal session so that your PATH adjustment loads and you
should be able to tab complete the command:

```
$ git ensu<tab>
$ git ensure-main
```

Note: that'll only work if you're in a folder that is a git repo!

## Wait what about master?

There's a movement afoot to change the default branch in a git repo from master
to main - check it:

> Many communities, both on GitHub and in the wider Git community, are
> considering renaming the default branch name of their repository from master.
> GitHub is gradually renaming the default branch of our own repositories from
> master to main.

https://github.com/github/renaming

So yeah, this project checks for main because we should be the change we want to
see in the world.

## Why would I want this?

I wrote this because I was tired of copy/pasting code like it from script to
script. I often found myself wanting to only execute a script if I was on the
main branch so now I can just do this:

```diff
#!/bin/bash

set -e

- if [ $(git branch --show-current) != "main" ]; then
-   echo "ERROR: must be on main branch"
-   exit 1
- fi
+ git ensure-main

# do something interesting
```
