---
title: 'Linux: ''su'' VS ''sudo'' VS ''sudo -i'''
tags:
- Linux
---

## su
enter root mode using root's password

## sudo 
use super user's privilege to execuate a command 

## sudo -i
enter root mode using a superuser's password

## su  VS sudo -i
The passwords used are different
su: must use root's password
sudo -i: can use any user's password who is in admin group

## Enable/Disable root user
Some systems did not enable root user (Some users in admin group).
Give root password will enable root

```
$sudo –i passwd root
Enter new UNIX password: [Set new password for root account]
Retype new UNIX password: [Confirm new password]
```

Delete password of root will disable root

```
$sudo passwd -dl root
```
