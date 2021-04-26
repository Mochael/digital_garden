---
title: Managing Ruby Versions with rbenv
tree_state: 🌱
---

rbenv works super similarly to other software version managers like pyenv for example.

### Installing new version of Ruby
- `rbenv install -l` command lists all recent stable versions of Ruby
- `rbenv install <version>` command installs the version of Ruby you write


### To get your terminal commands to use ruby from rbenv run this code
```
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
exec $SHELL
```

### Setting Ruby Version for Specific Directory
- change directory to your project and run `rbenv local <version>` to set the version of Ruby used whenever you are inside this directory.


### Check Versions of Ruby Installed
- `rbenv versions` lists out the versions of Ruby you have installed through rbenv