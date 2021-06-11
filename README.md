# How to made an Flask server from zero
## Full guidelines - Author is Rick Sanchez D634.

_From the void of your creation, please get an server now, with this paper you can do the important things so fast, very fast_

1. create and secure the server
**NEEDS :**
	- [ ] change ssh port number to made confusion
	- [ ] generate correct ssh keys pairs
	- [ ] setting up ssh keys and enable the pub key authentication
	- [ ] disable passwords auth methods
	- [x] disable root login
	- [ ] strong passwords
	- [ ] made rights levels to ssh hidden folder and inside
	- [x] enable compression on ssh
	- [ ] customise an banner ssh
	- [ ] enable filtering users allowed or deny
	- [ ] setting up firewall (here its UFW)
	- [ ] enable sshguard(same role than fail2ban)
	- [ ] use an non-root user over ssh
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

after that you can do `su john` the prompt ask the password (PAM managed) of the session to grant the access.

_password to enter in ssh from outside of the system is just poop in security level(on the cybersecurity Sanchez scale ,rules and methods) but to switch to another account is regular way but not the only way_

* create ssh keys on server and client correctly
**Client side**

the first question is, what is the algorithm you can choice and what is better in security because is the first need, please read all, is important:


First use this command to generate 
```

```


```

```


```

```


```

```


```

```

```

```






* setting up ssh daemon
### Configure SSHD (DAEMON of SSH)
**config file ready to use**
filepath of the _**SSH daemon**_ configuration: `/etc/ssh/sshd_config`
```
#       $OpenBSD: sshd_config,v 1.103 2018/04/09 20:41:22 tj Exp $

# This is the sshd server system-wide configuration file.  See
# sshd_config(5) for more information.

# This sshd was compiled with PATH=/usr/local/sbin:/usr/local/bin:/usr/bin

# The strategy used for options in the default sshd_config shipped with
# OpenSSH is to specify options with their default value where
# possible, but leave them commented.  Uncommented options override the
# default value.

Port 27019
#AddressFamily any
#ListenAddress 0.0.0.0
#ListenAddress ::

#HostKey /etc/ssh/ssh_host_rsa_key
#HostKey /etc/ssh/ssh_host_ecdsa_key
#HostKey /etc/ssh/ssh_host_ed25519_key

# Ciphers and keying
#RekeyLimit default none

# Logging
#SyslogFacility AUTH
#LogLevel INFO

# Authentication:

#LoginGraceTime 2m
PermitRootLogin no
#StrictModes yes
#MaxAuthTries 6
#MaxSessions 10

PubkeyAuthentication yes

# The default is to check both .ssh/authorized_keys and .ssh/authorized_keys2
# but this is overridden so installations will only check .ssh/authorized_keys
AuthorizedKeysFile      .ssh/authorized_keys

#AuthorizedPrincipalsFile none

#AuthorizedKeysCommand none
#AuthorizedKeysCommandUser nobody

# For this to work you will also need host keys in /etc/ssh/ssh_known_hosts
#HostbasedAuthentication no
# Change to yes if you don't trust ~/.ssh/known_hosts for
# HostbasedAuthentication
#IgnoreUserKnownHosts no
# Don't read the user's ~/.rhosts and ~/.shosts files
#IgnoreRhosts yes

# To disable tunneled clear text passwords, change to no here!
PasswordAuthentication no
PermitEmptyPasswords no

# Change to no to disable s/key passwords
ChallengeResponseAuthentication no

# Kerberos options
#KerberosAuthentication no
#KerberosOrLocalPasswd yes
#KerberosTicketCleanup yes
#KerberosGetAFSToken no

# GSSAPI options
#GSSAPIAuthentication no
#GSSAPICleanupCredentials yes

# Set this to 'yes' to enable PAM authentication, account processing,
# and session processing. If this is enabled, PAM authentication will
# be allowed through the ChallengeResponseAuthentication and
# PasswordAuthentication.  Depending on your PAM configuration,
# PAM authentication via ChallengeResponseAuthentication may bypass
# the setting of "PermitRootLogin without-password".
# If you just want the PAM account and session checks to run without
# PAM authentication, then enable this but set PasswordAuthentication
# and ChallengeResponseAuthentication to 'no'.
UsePAM yes

#AllowAgentForwarding yes
#AllowTcpForwarding yes
#GatewayPorts no
#X11Forwarding no
#X11DisplayOffset 10
#X11UseLocalhost yes
#PermitTTY yes
PrintMotd no # pam does that
PrintLastLog yes
#TCPKeepAlive yes
#PermitUserEnvironment no
Compression yes
#ClientAliveInterval 0
#ClientAliveCountMax 3
#UseDNS no
#PidFile /run/sshd.pid
#MaxStartups 10:30:100
#PermitTunnel no
#ChrootDirectory none
#VersionAddendum none

# no default banner path
Banner /var/sshd_banner

# override default of no subsystems
Subsystem       sftp    /usr/lib/ssh/sftp-server

# Example of overriding settings on a per-user basis
#Match User anoncvs
#       X11Forwarding no
#       AllowTcpForwarding no
#       PermitTTY no
#       ForceCommand cvs server
```

1) Build Minimal flask server

2) Create DB for user login and subscribe.

3) Intégration d'un éditeur de texte pour le/les auteur(s)

4) Créer mecanisme de publication de texte en flask, d'image, vidéo

5) And more...
