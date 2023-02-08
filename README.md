# Description
Gitui config with catppuccin theme and vim keybindings:

## Status

- [ ] _in progress_
- [x] _finished_
- [ ] _no longer continued_

## Table of contents

- [Description](#description)
- [Status](#status)
- [Table of contents](#table-of-contents)
- [Screenshots](#screenshots)
- [Technologies](#technologies)
- [Setup](#setup)
- [Known Issues](#known-issues)



## Screenshots

<![Gitui](./assets/gitui.png)>

## Technologies
- gitui

## Setup

Setup gitui. Add this config to '~/.config/gitui'

## MacOS
Add osxkeychain to credential helper:
```
git config --global credential.helper osxkeychain
```

Add to ~/.gitconfig:

```.gitconfig
[core]
  editor = /Users/jonas.leonhard/.local/bin/lvim
  pager = delta
```

## Known Issues / Missing Features

I Ran into an Gitui issue when using multiple git accounts:
Error: 'git: bad credentials'.Event though pushing and pulling the repository without gitui works.

This might be caused because a ssh-key is missing for you config because it is not beeing parse correctly (https://github.com/extrawurst/gitui/issues/495#issuecomment-1198777368). 

Create one, then add the ssh key required for your repository to be pulled/pushed:
```
ssh-add ~/.ssh/github
```

#### Example Creating a SSH key for github. Then add it to github.settings:
```
ssh-keygen -t ecdsa -C "example@gmail.com"
Type `github` in the first question
pbcopy < ~/.ssh/github.pub
ssh-add ~/.ssh/github
ssh -T git@github.com
```

This might also be required to beset again after a restart
---

