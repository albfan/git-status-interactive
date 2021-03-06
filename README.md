# git-loop

A helping hand to deal with your messy repo.

![git loop screencast](etc/git-loop-screencast.gif)

## Intro

**git-loop** is a handy keystroke saving for your git workflow. It starts as an expansion to *git status* performing a *git status --interactive* but quickly become a complete solution for daily workflow.

You can easily review your unstaged changes, add, commit, push, pull, with a few keystrokes.

## Features

- List files touched or new
- list files in new directories
- perform diff, add, rm, reset, checkout on selected files
- launch global commands (commit, pull, push)
- custom commands and actions: Add your favourite commands and alias to loop through `loop` section
- works on subdirs

```
$ git config loop.global-command <list of alias>
$ git config loop.<key>-command <list of alias>
```

These are mine

```
[loop]
   global-command = recommit rework
   diff-command = tdiff
```

See my [dotfiles](https://github.com/albfan/dotfiles/blob/master/gitconfig) for explanation of this alias

## Config

You can customize the editor and pager

*Showing the default values*
```
[loop]
   editor = vim
   pager = less
```

## Usage

Link script to your *PATH*:

    $ git clone <repo>
    $ cd <repo>
    $ ln -s git-loop ~/bin/

Use it:

    $ git loop

    1)  M file1
    2) ?? dir
    3) commit
    4) push
    5) pull
    6) clear
    7) quit

     file> 1

    1) diff
    2) add
    3) rm
    4) checkout
    5) reset
    6) clear
    7) quit

     action (file1)> 1
    ....
    + added this
    - deleted that
    ....

     action> 2

    1) M  file1
    2) ?? dir
    3) commit
    4) push
    5) pull
    6) clear
    7) quit

     file> 2

    listing files in (dir)

    1) file2
    2) file3
    3) clear
    4) quit

     dir> 1

    1) add
    2) less
    3) clear
    4) quit

     action> 2

     file2 contains this

     action> 1

    1) M  file1
    2) A  dir/file2
    3) ?? dir/file3
    4) commit
    5) push
    6) pull
    7) clear
    8) quit

     file> 7  #or type quit

    $

## Contribution

This snippet is focus on make your life easier, so any contribution is appreciated. It is evolving by rating "benefit/time" so if you have time, is pretty sure your PR will be accepted. Feel free to open issues or send PR.

By now, read the **TODOs** inside the script to find something useful to work on. Clearly a big step will be to recode script in perl.

