ansible-deploy
==============

This is a set of ansible roles to deploy a bunch of things I use from day to
day. To use it, you need to have an ansible (tested on version 2.3.0.0)
tooling setted up.

This repo is organized next way:


```
.
|-- group_vars
|-- host_vars
|-- inventory
|-- roles
`-- vars
```

*group_vars* contains variables which are common for specific group types, like
~all~ or ~docker~

*host_vars* contains variables for hosts, such as user name and hostname and IP

*inventory* lists all the inventory files. As this repo is used for different
projects but the same roles are used, separate inventory files are needed

*roles* lists all available ansible roles

*vars* contains variables for different OS types or for separate playbooks


Main playbooks there are:

* dotfiles.yml - sets the dotfiles I use everyday
* xapps.yml - sets a configs for X apps
* monitoring.yml - setup collectd to nodes


To apply any of there all you need is just


```
$ ansible-playbook -i hosts <playbook_name.yml> [--vault-password-file ~/.vault_pass.txt]
```
