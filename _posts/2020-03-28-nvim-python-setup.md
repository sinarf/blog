---
layout: post
title: Yet another nvim for Python 3 development setup
date: 2020-03-28 16:20 +0100
tags: [nvim, python]
---

## Introduction


I am playing with Python these days and since I love tools, I'm looking for the right tool.

My editor of choice is vim (now neovim) and there is a lot of stuff for Python development.
See the Links section below for a good read.

## What was my problem with existing resources?

- Many tutorial gives you a `.vimrc` file to drop in your Home directory.
- Python-mode seems promissing, but I couldn't make work the refactoring part.
- Some of the plugin used are obsolete

## What is my goal?

Having a real setup tutorial, with every line of configuration explained.

I would like to have these feature:

- Code completion
- PEP8 autoformating
- Code lint
- Simple access to documentation
- A simple way to run a script
- A simple way to run unit test

Bonus features would be:

- Automaticaly run the test on every save
- A simple way to run a script with parameters

## Refactor

- [rope vim plugin](https://github.com/python-rope/ropevim)

For the refactoring part, we'll use rope.

First install the dependencies:

```
pip install rope ropemode ropevim
```
Install the vim plugin

```
Plug 'python-rope/ropevim'
```
I enable this options. 
```
"Rope                                                                                                                                                                          
let ropevim_vim_completion=1
let ropevim_extended_complete=1
	
```

## Code validation with flake8

- [flake8](https://github.com/nvie/vim-flake8)

First install the dependency:

```
pip install flakes
```
Install the vim plugin

```
Plug 'nvie/vim-flake8'
```
I enable this options. 
```
"Run each time you save Python file
autocmd BufWritePost *.py call flake8#Flake8()
"flake8
let g:flake8_show_in_gutter=1
let g:flake8_show_in_file=1
	
```

## Code completion wich coc and jedi

I am already using coc as my completion tool. To make it work with python I add to install the plugin python for coc. 
In vim run: 

```
CocInstall coc-python
```
Then I had to install the jedi library : 

```
yaourt -Syu python-jedi
```

## Conclusion

I haven't made the unit test work yet, but I already have:


- Code completion
- PEP8 autoformating
- Code lint
- Simple access to documentation
- A simple way to run a script

I still missing:

- A simple way to run unit test


## Links

- [My neovim dotfiles](https://framagit.org/sinarf/dotneovim)

