## What are in the repo
    dotfile
    ├── astylerc
    ├── editorconfig
    ├── gitconfig
    ├── oh-my-zsh
    ├── sublime
    |   ├── monokai-custom
    |   ├── Preference.sublime-settings
    |   └── SublimePackages.md
    ├── vim
    |   └── bundle
    │       └── vundle
    ├── vimrc
    ├── wgetrc
    └── zshrc

## Why is the file or directory here

- astylerc - the config for **astyle** which is a format tool for *C*, *C++*, *C#*, *Java*
- editorconfig - the config for vim bundle **js-beautify**
- gitconfig - the config for **git**
- oh-my-zsh - git submodule, the directory `.oh-my-zsh` for **zsh**
- sublime - git submodule, the Preference and Monokai-custom for _Sublime Text 2_
- vim - the directory `.vim` for **vim**
- vimrc - the config for **vim**
- wgetrc - the `http_proxy` config for **wget**
- zshrc - the config for **zsh**, firstly generated by **[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)**, and some other config added by me

## What vim bundles are included in vimrc

    Bundle 'gmarik/vundle'
    Bundle 'tomasr/molokai'
    Bundle 'scrooloose/nerdtree'
    Bundle 'jistr/vim-nerdtree-tabs'
    Bundle 'maksimr/vim-jsbeautify'
    Bundle 'einars/js-beautify'
    Bundle 'scrooloose/nerdcommenter'
    Bundle 'plasticboy/vim-markdown'
    Bundle 'kchmck/vim-coffee-script'
    Bundle 'groenewege/vim-less'
    Bundle 'mattn/emmet-vim'
    Bundle 'drmingdrmer/xptemplate'
    Bundle 'mattn/calendar-vim'
    Bundle 'terryma/vim-multiple-cursors'

## Tasks & Requirement
If you want to do all tasks(except `sublime`) below, just run

    make

or do a specific task by run

    make <taskname1>[ <taskname2> <tasknameN> ...]

![screenshot](./screenshot.jpg)

- ### Task `vimrc`
    1. Requirements: `git`, `vim`
    2. Setup:

            make vimrc

    After above, you can override the system vim with the one installed by `homebrew`.(OS X only. This is optional, but recommended, because system vim can't use system clipbord via register `+`)

        brew install macvim --override-system-vim

- ### Task `gitconfig`
    1. Requirement: `git`
    2. Setup:

            make gitconfig

- ### Task `astylerc`
    1. Requirement: `astyle`. If you have installed `astyle` and press `Q` in vim, astyle will be used to format the file.
    2. Setup:

            make astyle

- ### Task `wgetrc`
    1. Requirement: `wget`
    2. Setup:

            make wgetrc

- ### Task `zsh`
    If you have installed new zsh(installed in `/usr/local/bin/zsh`) by `homebrew`, and want to use it as **login shell** instead of the **old** system zsh(`/bin/zsh`), add `/usr/local/bin/zsh` to your `/etc/shells` to make it to be **standard shell**. Otherwise, the setup will use system zsh.

        sudo su
        echo "/usr/local/bin/zsh" >> /etc/shells
        exit
    1. Requirements: `git`, `zsh`
    2. Setup:

            make zsh

- ### Task `sublime`
    If you use Sublime Text 2, this task will add user Preference for it, and also add a [`Monokai-custom`](https://github.com/Jeremial/sublime-monokai-custom) theme which supports Markdown file highlight.
    1. Requirement: `git`, `Sublime Text 2`
    2. Setup: **bakup your preference file first!**

        If you are using OS X, just run

            make sublime

        If you are using Linux, set `SUBLIMEPATH` first. e.g

            SUBLIMEPATH=~/sublimetext2 make sublime
    3. Install sublime packages(optional). You can see what sublime packages I used in [SublimePackages.md](sublime/SublimePackages.md).

## What are required optionally
*Note*: __These softwares or scripts are not necessary, but recommended.__

- astyle - required by **astylerc**

        # OS X only
        brew install astyle

- Kaleidoscope( _OS X only_ ) - an excellent difftool when input `git difftool`
- git-extras - some useful tools for git, install from <https://github.com/visionmedia/git-extras>( _Linux, OS X_ ) or

        # OS X only
        brew install git-extras

- git-flow - a post about git-flow: [a-successful-git-branching-model](http://nvie.com/posts/a-successful-git-branching-model/), install from <https://github.com/nvie/gitflow>( _Linux, OS X_ ) or

        # OS X only
        brew install git-flow

## LICENSE

The MIT License (MIT)

Copyright (c) 2013 Jeremial

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.