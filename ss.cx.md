---
layout: page
title: server setup
---

 ss.cx initial setup notes

`168.235.71.126` `ss.cx`

## initial setup

* debian 14.04 on ramnode ! nope! switched to debian 7 minimal

* [admin page](https://vpscp.ramnode.com/)

    apt-get update
    apt-get upgrade

set root password using ramnode's admin interface


## user stuff

    adduser ajm

enable sudo

    gpasswd -a ajm sudo
    apt-get install sudo

turn off root login

    # apt-get install nano
    # nano /etc/ssh/sshd_config

    edit to:
    PermitRootLogin no

    Port 22

## Ssh Stuff

ssh info from [digital ocean](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2)

generate an ssh key (~/.ssh/horatio)

    mac# ssh-keygen -t rsa

send it over

    mac# cat ~/.ssh/horatio.pub | ssh ajm@ss.cx "mkdir -p ~/.ssh && cat >>  ~/.ssh/authorized_keys"

locally configure ssh to use the right key with the new host [from here](http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/)

edit ~/.ssh/config
    Host horatio
      Port 22
      HostName ss.cx
      User ajm
      IdentityFile ~/.ssh/horatio

make sure it works

    mac# ssh -i ~/.ssh/horatio root@ss.cx

    # reload ssh

## firewall

see [reference](https://www.digitalocean.com/community/tutorials/additional-recommended-steps-for-new-ubuntu-14-04-servers)

    sudo apt-get install ufw
    sudo ufw allow 80/tcp
    sudo ufw allow 22/tcp
    sudo ufw logging on
    sudo ufw enable
    sudo ufw status

## time

    sudo dpkg-reconfigure tzdata

    sudo apt-get install ntp

<!-- ## swap

    sudo fallocate -l 512M /swapfile
    sudo chmod 600 /swapfile
    sudo mkswap /swapfile
    sudo swapon /swapfile
    sudo sh -c 'echo "/swapfile none swap sw 0 0" >> /etc/fstab' -->

## nginx

    apt-get install ngnix

    rm /etc/nginx/sites-enabled/default
    nano /etc/nginx/sites-available/horatio # contents below
    cp /etc/nginx/sites-available/horatio /etc/nginx/sites-enabled/

as follows:

    # inspired by https://gist.github.com/jagger27/ebda33fefe4032773594
    server {
        listen 80;
        # to disallow anything other than what's below (like a direct IP)
        server_name _;
    }

    server {
        listen       80;
        server_name  ss.cx www.ss.cx;
        root   /usr/share/nginx/www;
        index  index.html index.htm;

        # matches [example.com]/~[username]
        # and maps it to /home/[username]
        location ~ ^/~([\-\_\w]*)(.*)$ {
            alias  /home/$1/public_html$2;
        }

        # error_page  404              /404.html;
    }

## personal github on server

    ssh-keygen -t rsa -C "a@monks.co"
    cat ~/.ssh/horatio-ajm.pub

then copy and paste into github admin interface

    # start the ssh-agent in the background
    eval "$(ssh-agent -s)"
    # Agent pid 59566
    ssh-add ~/.ssh/id_rsa

from https://help.github.com/articles/generating-ssh-keys/#platform-linux

## local mail

    apt-get install postfix
    apt-get install alpine

## irc

    apt-get install ngircd
    nano /etc/ngircd/ngircd.conf

no password
port: 6667

    apt-get install irssi
    sudo ufw allow 6667/tcp


## other installs

    apt-get install tmux
    apt-get install finger
    apt-get install cowsay
    apt-get install tree

https://github.com/zolrath/wemux


## ruby

    \curl -sSL https://get.rvm.io | sudo bash -s stable

    add to skel .bashrc:

    [[ -s /usr/local/rvm/scripts/rvm ]] && source /usr/local/rvm/scripts/rvm

add self (and other users) to rvm group: (from [here](http://unix.stackexchange.com/questions/102678/making-ruby-available-to-all-users))

    sudo usermod -a -G rvm <user>

install ruby

    rvm install 2.2.0

## node

sudo su
curl -sL https://deb.nodesource.com/setup | bash -
apt-get install -y nodejs
