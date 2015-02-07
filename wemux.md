# Pair programming with `wemux`

I installed a utility called [wemux](https://github.com/zolrath/wemux) to facilitate sharing terminal sessions. There's a pretty good readme on their [github page](https://github.com/zolrath/wemux#host-commands)

Here's a quick overview of how to use it.

## Sharing your terminal

Type `wemux start` to start a shared session. You can then run `wemux stop` *from outside of that session* to end it. If someone's being reckless, you can use `wemux kick <username>` to kick them out of your session.

You can use `wemux users` to display a list of who's connected to your session. 
## Connecting to a shared terminal

Type `wemux mirror` to connect to the server in read-only mode, or `wemux pair` to share control.

I have rogue mode turned off on this server.
