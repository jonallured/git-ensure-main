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
