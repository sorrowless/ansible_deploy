ansible-deploy
==============

This is a set of ansible roles to deploy a bunch of things I use from day to
day. To use it, you need to have an ansible (tested on version 2.3.0.0)
tooling setted up.

This repo is organized next way:


```
.
|-- dotfiles.yml
|-- xapps.yml
|-- hosts
|-- roles
|   |-- git
|   |-- screen
|   |-- vim
|   |-- xbindkeys
|   `-- zsh
`-- vars
|   |-- dotfiles_vars.yml
|   `-- xapps.yml
`-- README.md
```


where *roles* directory contains all the roles which are used in the playbooks,
*hosts* is an inventory file with hosts list, README.md is the file you are
reading right now and bunch of *.yml* files are the playbooks to use. Also
there is *vars* directory with the variables needed to roles. I have to keep
them encrypted by ansible-vault, but you have not obliged to do this.

Main playbooks there are:

* dotfiles.yml - sets the dotfiles I use everyday
* xapps.yml - sets a configs for X apps

To apply any of there all you need is just


```
$ ansible-playbook -i hosts <playbook_name.yml> [--vault-password-file ~/.vault_pass.txt]
```
