# Git 101

We are using Git version 2.8.1, but any recent version should be good.
It's recommended to learn the `git` command line tool for full
cross-platform experience and a deeper understanding of Git itself.

There are (too) many Git tutorials on the internet. Here we post
references to our favorites.

## Install

#### Windows

Install [Git for Windows][].

During the install process, choose these recommended settings:

* Use Git from the Windows Command Prompt
* Use OpenSSH
* Checkout Windows-style, commit Unix-style line endings
* Use Windows' default console window
* Enable file system caching

[Git for Windows]: https://git-scm.com/download/win

#### Linux

Install via the package manager:

```sh
sudo apt-get install git
```

## Interactive tutorials

#### Hello world

If you're new to Git, learn the following commands: `checkout`, `branch`,
`pull`, `push`, `merge`.

Use GitHub's [Hello World][] to learn how to create a feature branch, commit
changes, and issue a pull request.

[hello world]: https://guides.github.com/activities/hello-world/

#### Githug

[Githug](https://github.com/Gazler/githug) is a great gamified way to
learn Git in couple hours. After finishing 50+ real-world scenarios
you will have a pretty good idea about what and when you can do with
Git.

## Cheatsheets

#### Git pretty

[So you have a mess on your hands?](http://justinhileman.info/article/git-pretty/)

## Scenarios

#### Sync your local repo

Don't commit your changes directly to master.
It would make workflow messy.

Always create a branch for your changes.

```sh
# switch to master branch

# fetch updates all remote branch references in the repo and all submodules
# --all : tells it to do it for all remotes (handy, when you use your fork)
# -p : tells it to remove obsolete remote branch references (when they are removed from remote)
git fetch --all -p

# pull updates your local files
# you should call this command ONLY from master branch
git pull origin master

# update submodules: this checks the submodules out to the commit recorded in the superproject
git submodule update
```

Then switch to your branch and do rebase

```
git rebase master
```