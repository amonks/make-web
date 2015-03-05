---
layout: page
title: editing
---

# Editing files on the server using a text editor on your computer

Let's try to edit a file on the server. First we'll try it out from right inside the terminal, then we'll talk about a couple other ways.

## A good first website

Inside your home folder (`/home/[yourname]`, the directory you log in to), you'll see a folder called `public_html`. Anything inside that folder will be served over the internet to `http://ss.cx/~[yourname]/[whatever]`.

To try this out, you'll need to make a file called `hello` inside your `~/public_html` directory.

### steps

1.  `cd` into your `~/public_html` directory
2.  type `nano hello.html` to edit a new file called `hello.html`
3.  add some text to that file and save. Note that in the command line, the `^` symbol refers to the `ctrl` key.
4.  visit `http://ss.cx/~[yourname]/hello.html` and see the text you wrote.

### exercises

1.  visit `http://ss.cx/~yourname/` and see the text there.
2.  Figure out what file that text comes from.
3.  Edit that file to see if you're right.
