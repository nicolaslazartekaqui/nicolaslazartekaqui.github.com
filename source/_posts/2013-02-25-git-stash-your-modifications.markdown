---
layout: post
title: "Git - Stash your modifications"
date: 2013-02-25 16:38
comments: true
categories: git
---

During the development of a project in Git, it may be necessary to modify the branch without losing changes already made in another branch.

Git allows you to save the changes made and work on them later using the `git-stash`.

### Usage

    $ git status
    # On branch master
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    # modified:   README.rdoc

in this case `README.rdoc` has changes, we save them using `git-stash`

    $ git stash
    # Saved working directory and index state WIP on master: 4a9db3e first
    # HEAD is now at 4a9db3e first

changes saved, the project is now in version without changes

    $ git status
    # On branch master
    # nothing to commit (working directory clean)

to see which stashes you’ve stored, you can use `git stash list`

    $ git stash list
    # stash@{0}: WIP on master: 4a9db3e firs

You can reapply the stash using the command `git stash apply`. If you have more than one stash, you can specify which stash you want to apply, see the example:

    $ git stash apply stash@{0}
    # On branch master
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    # modified:   README.rdoc

To drop the stash use the command `git stash drop <NAME_STASH>` or when reapply the stash you can use the command `git stash pop <NAME_STASH>`, this way you reapply and drop the stash at the same time.

Is possible to do more things with this git tool, see more in this [link](http://git-scm.com/book/en/Git-Tools-Stashing#Creating-a-Branch-from-a-Stash).
