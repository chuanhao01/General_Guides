# My Terminal Setup

This guide will be on how to get my terminal setup.  
TL|DR: `I3`, `Konsole`, `Zsh`, `oh-my-zsh` and `Powerlevel10k`
 
## Table of Contents
**TOC HERE**

# General Dependencies

For this guide I will assume you have `Arch Linux` (I use Arch BTW :D Had to put this in) and the desktop enviroment `I3`. (Although at this point its only a window manager)  

I might do a guide separately on `I3` in the future because that in itself takes quite a while.  

# Guide

To give a bit more background for my terminal setup, I chose `Konsole`, mainly because it looked nice and had the ability to choose profiles. (Maybe in the future I might pick `Alacritty`)  

I chose `Zsh`, `oh-my-zsh` and `Powerlevel10k` mainly to theme my terminal prompt. (This was long overdue, seriously if you use linux as your desktop enviroment, you need this)  

Now, without further ado, let get on with the guide

## Installing `Konsole`  

To install `Konsole` on arch, simply use pacman.  

```bash
sudo pacman -S konsole
```

Note: Icons and such will not work yet because we do not have the entire `KDE Plasma` set. The wiki has more information.

## Installing `Zsh`

This is also quite simple, but we do have to keep in mind to change our user's default shell after installing `Zsh`.

```bash
# Installing zsh
sudo pacman -S zsh

# Change default shell
# Note /bin/zsh is the path to your new default shell
chsh -s /bin/zsh
```

You have to logout and log back in for you to see the changes to your default shell.  

**Sidenote:**

`Zsh`, much like `Bash` uses a user and default config file.  
This file is the `.zshrc` and `.bashrc` respectively.  
They can usually be found in the home directory. (`~/`)

To get your current terminal to get/source the configs in the config files you can do:  
```bash
# For zsh
source ~/.zshrc

# In general
# Replace PATH_TO_CONFIG with the path to the config file
source PATH_TO_CONFIG
```

## Installing `oh-my-zsh`  

For this part you should be referring to the [`oh-my-zsh`](https://github.com/ohmyzsh/ohmyzsh) github's page.  
More information can be found there.  
Below will just be the general steps needed to install `oh-my-zsh`.  


# References

- Arch Linux
- I3
- Konsole
  - Arch Wiki
  - Website
- Zsh
- oh-my-zsh
- Powerlevel10k

### Updates


<!-- 
REMOVE ME WHEN COPYING

Make sure to add Table of Contents (TOC) when done
Make sure to generate section numbers when done

Take note to comment out the first two sections when doing this
 -->


