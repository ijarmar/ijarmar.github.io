---
title: How to replace xfwm4 with bspwm on XFCE environment Arch Linux
published: true
---

## Prerequisites 

Working XFCE Desktop Environment and Git

## Installing bspwm AND sxhkd

- bspwm (Window Manager)
```bash 
$ cd /opt
$ git clone https://aur.archlinux.org/bspwm-git.git
$ cd bspwm-git
$ makepkg -si
```
- sxhkd (X hotkey daemon)
```bash
$ sudo pacman -S community/sxhkd
```

## Configurations

First create configuration directories with rc files
```bash
$ mkdir ~/.config/bspwm
$ mkdir ~/.config/sxhkd
```

Copy example config files
```bash
$ cp /opt/bspwm-git/examples/bspwmrc ~/.config/bspwm/bspwmrc
$ cp /opt/bspwm-git/examples/sxhkdrc ~/.config/sxhkd/sxhkdrc
```

Make files executable
```bash
$ chmod +x ~/.config/bspwm/bspwmrc
$ chmod +x ~/.config/sxhkd/sxhkdrc
```

## Optional: change cursor behavior to normal

In your `bspwmrc` file add the following line
```text
# other stuff

xsetroot -cursor_name left_ptr &
```

## Change xfce settings to use bspwm

Simply enter this line
```bash
$ xfconf-query -c xfce4-session -p /sessions/Failsafe/Client0_Command -t string -sa bspwm
```

Reboot and you should be loaded into xfce with bspwm
