---
layout: post
title: "Configure the font and size of a terminal (No GUI)"
categories: linux, fedora, command-line
---

When running a terminal with no GUI installed, the font display might no be too pleasant to look at. This can be arranged with the following.

Start by installing console-setup.

```shell
sudo dnf install -y console-setup
```

After the installation, you will have new terminal ready fonts. 
They'll be located here: ***/usr/share/consolefonts***

You can set the following in your .bashrc or .zshrc file, so that your preferred font is selected at startup. 

```shell
if [[ $TERM == linux]]
then
  setfont /usr/share/consolefonts/Lat38-Terminus22x11.psf.gz
fi
```

