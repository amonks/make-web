---
title: mosh
layout: page
---

if you install [mosh](https://mosh.mit.edu/#) on your mac, you can use it to connect rather than ssh. The syntax is the same, just `mosh <yourname>@ss.cx` rather than `ssh <yourname>@ss.cx`.

Mosh, which stands for 'mobile shell', is a layer on top of ssh that's much better at maintaining connections over wifi, cellular, or otherwise shaky networks. It also uses less bandwidth, and gets rid of the typing lag you might experience over ssh.
