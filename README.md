# How to made an Flask server from zero
## Full guidelines - Author is Rick Sanchez D634.

_From the void of your creation, please get an server now, with this paper you can do the important things so fast, very fast_

1. create and secure the server
* create an user on the Arch Linux server node
if you are not root, just add  `sudo`  at begin like an prefix of all commands
```
pacman --sync sudo
useradd --create-home john
passwd john
usermod --append --groups wheel john
vim /etc/sudoers
```
in `/etc/sudoers` just you can modify the sudo access to grant the privileges of your new user, if you want be super user with this.

* setting up ssh daemon
**NEEDS :**
	* change ssh port number to made confusion
	* setting up ssh keys and enable the pub key authentication
	* disable passwords auth methods
	* disable root login
	* strong passwords
	* made rights levels to ssh hidden folder and inside
	* enable compression on ssh
	* customise an banner ssh
	* enable filtering users allowed or deny
	* setting up firewall (here its UFW)
	* enable sshguard(same role than fail2ban)

**config file ready to use**
filepath of the _**SSH daemon**_ configuration: `/etc/ssh/sshd_config`
```

```

1) Build Minimal flask server

2) Create DB for user login and subscribe.

3) Intégration d'un éditeur de texte pour le/les auteur(s)

4) Créer mecanisme de publication de texte en flask, d'image, vidéo

5) And more...
