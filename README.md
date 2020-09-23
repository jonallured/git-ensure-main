# Git Ensure Main

This is an extension to git that ensure one is on the main branch:

```
$ git branch --show-current
main
$ git ensure-main
$ git checkout -b feature-branch
$ git branch --show-current
main
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

, something like this:

```
# in a file like ~/.zshrc
export PATH=path/to/code/folder/git-ensure-main/bin:${PATH}
```

Then open a new terminal session so that your PATH adjustment loads and you
should be able to tab complete the command:

```
$ git ensu<tab>
```

Note: that'll only work if you're in a folder that is a git repo!
