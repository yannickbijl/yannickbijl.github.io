---
layout: post
date: 2023-02-04 00:00:00 +0100
tags: [Linux, BASH]
categories: Software-Development Tools
title: 'Making Aliases'
---

Many commands in the linux terminal environment are highly customizable using flags and options. Often we use the same commands with the same settings. Aliases can be used to set the flags and options by default, or name new commands with these behaviors. Thus instead of typing `ls -a -l -t` or the shorter form `ls -alt`, we can create an alias `lt` that does the same. I basically use aliases to have human readable format enabled by default for commands such as `ls` and `df`.

An alias can be created in the terminal using the `alias` command as seen below. The basic syntax is `alias <name>="<command>"`. Any valid command can be put in there, even with pipes (`|`) chaining multiple commands into one.

```bash
alias lt="ls -alt"
```

However, simply executing this command will only allow you to have this command for the current session. To have these aliases available to you every time we will put them in the shell startup configuration script, which is run each time when opening a terminal. In the case of the BASH shell it is `.bashrc`, for the Oh-My-Zsh shell it is the file `.oh-my-zsh`. The standard Zsh shell uses `.zshrc`.

Though it is possible to put the aliases almost anywhere in the file, it is recommended to put them at the end. This is to prevent anything breaking during setup of the terminal. Similarly, be careful of the order of the aliases. If a new alias uses an existing one, it must come after it in the configuration script.

When you create a lot of aliases it might be better to create a separate file for them. This can basically be any file. It is recommended to have this file in your home directory and be hidden (starting with a `.`). In your shell configuration script you put the following code. Replace `< >` with your own filename. This will call the file with your aliases and thus loading them into your terminal environment.

```bash
if [ -e $HOME/<.bash_aliases> ]; then
    source $HOME/<.bash_aliases>
fi
```

With this you can start making your own aliases. This can help with automating some simple commands, making the defaults useable and sensible. You could also automate your ssh login, though be careful with passwords. In short you can use aliases to make your development processes nicer and suited for your needs.
