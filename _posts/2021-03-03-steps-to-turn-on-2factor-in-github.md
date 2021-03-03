---
title: Steps to after turning on 2factor in Github
tags:
- Github
---

# Two-factor is required soon in Github
## Install ssh
	sudo apt install openssh
## Generate ssh key
	ssh-keygen -t ed25519 -C "**@***.com"

## Add key to ssh agent
	open ~/.ssh/config

### Add the following to config file
	Host *
		AddKeysToAgent yes
		UseKeychain yes # depends on if password specified in the last step
		IdentityFile ~/.ssh/id_ed25519
     
### Execuate ssd-add
	ssh-add -K ~/.ssh/id_ed25519
	
## Add pubkey to Github
Settings -> SSH and GPG keys -> paste pubkey

## Get Personal Access Tokens 
### Once 2factor turned on, password is on longer working.
### Obtain PATs
settings -> Developer settings -> personal access tokens


Username does not affect.
