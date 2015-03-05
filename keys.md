---
layout: page
title: ssh keys
---

# Connecting without a password

ssh info from [digital ocean](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)

generate an ssh key (~/.ssh/horatio)

    mac# ssh-keygen -t rsa

send it over

    mac# cat ~/.ssh/horatio.pub | ssh ajm@ss.cx "mkdir -p ~/.ssh && cat >>  ~/.ssh/authorized_keys"

locally configure ssh to use the right key with the new host [from here](http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/)

edit ~/.ssh/config on the mac

    Host horatio
      Port 22
      HostName ss.cx
      User ajm
      IdentityFile ~/.ssh/horatio

make sure it works

    mac# ssh -i ~/.ssh/horatio root@ss.cx

    # reload ssh

