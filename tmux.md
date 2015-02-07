---
title: tmux
layout: page
---

# tmux / screen

Sometimes it's helpful to have your commands keep running and your session preserved even if you disconnect from SSH. Other times it would be cool to have multiple terminal sessions active at once, perhaps to edit two files at once or to keep a program running while making changes somewhere else. Still other times, it would be nice to have multiple people look at the same terminal so you can work together.

One way to accomplish all of these things is with programs like `tmux` or `screen`. They're called 'terminal multiplexers'. The `tmux` website explains:

>    What is a terminal multiplexer? It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more.

This server has `tmux` installed on it, so that's what we'll use.

## Basic tmux usage

The first step is to create a tmux session. Type `tmux new-session`. Sometimes, if I'm starting a session to work on a particular project, I'll name the session something like `tmux new-session -s cool3dthing` so I can easily come back to it later. Now you're connected to `tmux`. If you quit ssh and come back later, you can run `tmux attach` to reconnect to this same session.

To control tmux itself, you'll almost always use `control-b` (often shortened to `^b`) followed by the shortcut for a particular command.

## windows and panes

`tmux` has two ways of opening more terminals: windows and panes. A window takes up the whole terminal window, and can be split into panes. Let's start by splitting the current window into two panes: type `control-b` then `%` (`^b %`). You can use `^b` followed by an arrow key to switch between the panes.

To make a new window, use `^b c`, you can then use `^b w` to get a list of windows that you can switch between.

## list of commands

attach to tmux session:

    tmux attach

detach when you're done:

    ^B d

## other commands

*    `^B t` current time

*    `^B "` split horizontal

*    `^B %` split vertical

*    `^B [arrow keys]` navigate between panes

## Sharing

For sharing sessions, I've installed a helper ontop of tmux called wemux. There's some more info at [this page](wemux)
