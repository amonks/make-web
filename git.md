---
layout: page
title: git
---

# Git

## configure git

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

## generate a key

from [github docs](https://help.github.com/articles/generating-ssh-keys/#platform-linux)

    ssh-keygen -t rsa -C "a@monks.co"

    # start the ssh-agent in the background
    eval "$(ssh-agent -s)"
    # Agent pid 59566
    ssh-add ~/.ssh/id_rsa

## add the key to your github account

visit the [github ssh settings page](https://github.com/settings/ssh)

add key, paste contents of `cat ~/.ssh/id_rsa.pub`

## test

    ssh -T git@github.com
