github demo
===========

This is for a quick demo of github!

## Basic Terminal Commands

### `cd`

change directory (switch folders)

* `cd` (drag folder from finder)

* `cd ~/Desktop`

### `ls`

list contents of current directory

* `ls -a` include hidden files

* `ls -al` include hidden files in nice detailed list

* `ls ~/Desktop` list the stuff on your desktop

### `pwd`

where am I? (print working directory)

## Basic Git Commands ([git - the simple guide](http://rogerdudler.github.io/git-guide/)) explains this better than I can

### `git clone [url]`

download the whole repository at the given url

* `git clone https://github.com/amonks/ghd.git`

### `git add`

start tracking a file

* `git add .`: add everything the current directory (`.`)

* `git add index.html`: add the index.html file only (equivalent to `git add ./index.html`)

### `git commit -m "message"`

commit your changes into git, including a short message making note of what you changed

* `git commit -am "I changed many files"` automatically add anything that's changed (note the `-a`)

* `git commit -m "Here's a short description of stuff I changed"` commit any changes to files you've already `git add`ed

### `git remote add [remote] [url]`

add a remote repository

* `git remote add origin https://github.com/amonks/ghd.git` create a remote called `origin` from amonks's `ghd` project on github. People usually call their main remote `origin` for some reason.

### `git push [remote] [branch]`

publish your changes to a remote repository

* `git push origin master`. The default branch is called `master`.

* `git push origin gh-pages` push to a branch called `gh-pages`

### `git pull [remote] [branch]`

pull changes from a remote repository

* `git pull origin master` get all the changes from the `master` branch at the `origin` remote

* `git pull origin gh-pages` get all the changes from the `gh-pages` branch at the `origin` remote

## links

### basic

*   [git - the simple guide](http://rogerdudler.github.io/git-guide/)

*   [getting to know the command line](http://www.davidbaumgold.com/tutorials/command-line/)

*   [mastering markdown](https://guides.github.com/features/mastering-markdown/)

*   [github app](https://mac.github.com/)

*   [getting started with github pages](https://guides.github.com/features/pages/)

### lol advanced

*   [understanding the github flow](https://guides.github.com/introduction/flow/)

*   [OG git flow post](http://nvie.com/posts/a-successful-git-branching-model/)

