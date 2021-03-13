---
title: SSHing into AWS and Running Things
tree_state: 🌱
---

## Setup
1. Create SSH Key
```
ssh-keygen
```
2. In AWS terminal register your key:
	1. `mkdir -p ~/.ssh`
	2. `vim ~/.ssh/authorized_keys` and copy the contents of your entire local public key file into this that you generated with step 1
	3. In an AWS jupyterhub terminal you can find our your username with `whoami`
	4. set the command `jhub_ssh` to ssh into your AWS jupyterhub
	```
	alias jhub_ssh='ssh -i <local path to public key> <username>@<AWS ec2 instance>'
	```

## How to Get In
`jhub_ssh`

## TMUX
Once you have ssh'd in you can run `tmux` to run a python script that will keep running once you exit the terminal.