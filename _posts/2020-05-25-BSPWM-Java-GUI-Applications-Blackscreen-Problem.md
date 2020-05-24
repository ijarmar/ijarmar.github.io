---
title: BSPWM Java GUI Application Blackscreen Problem
published: true
---

# Problem:

Application refuses to show anything but black screen after it has been loaded. 

# Solution:

Install `wmname` - Window Manager impersonator. This should work on all Arch-based distributions 

```bash
# pacman -S community/wmname
```

Update your `~/.config/bspwm/bspwmrc` configuration with this line at the bottom of the file.

```bash
wmname xfwm4 # or any other popular window manager
```
