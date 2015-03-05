---
layout: page
title: connecting
---

# Connecting to the server

To connect to the server, you'll need to use something called SSH—short for Secure Shell. SSH is a super old utility, a relic from when an institution might have had one or two computers that people would connect to and use from remote terminals. We use the same program today to connect to web servers that might physically be thousands of miles away in a data center. Ours is in New York.

## Getting an ssh terminal

Anyway, we need an SSH terminal, also called an SSH client. What to do depends on what kind of computer you're on.

### Macs

If you're on a Mac, Terminal.app is a good choice (It's what I use). You'll find it inside the `Utilities` folder inside your `Applicatuons`folder. Or by using the shortcut `cmnd-space` to open Spotlight, and typing `Terminal`.

### Windows

If you're on Windows, Google 'windows ssh client' and see where that gets you. I think I used PuTTY one time.

### Linux

If you're on Linux, I'm going to assume you're technically savvy enough to find your terminal.

### iPhone

I use an app called `Prompt` to connect to the server from my iPhone. I'm sure there are Android equivalents.

## Connecting

The address of our server is `ss.cx`. You should have gotten a username and password, let me know if you haven't. Type `ssh [your-username]@ss.cx` to connect. My username is `ajm`, so I use `ssh ajm@ss.cx`.

The server will ask for your password. You won't be able to see what you're typing—it's an older version of showing dots or stars—but press the enter key when you're done.

## First Steps

Use Google to learn the following:

*   What directory you're in
*   What files+folders are in that directory
*   How to change to a different directory
*   How to create a new directory
