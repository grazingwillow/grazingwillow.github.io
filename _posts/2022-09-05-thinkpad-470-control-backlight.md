---
layout: post
title: "Control the backlight on linux via commandline (Thinkpad)"
categories: linux, thinkpad, command-line
---

Using the command line, you can easily control the backlight. 
Let's increase both the laptop screen backlight, and the keyboard backlight.

The configuration is altered by editing a text file.
Using a Thinkpad laptop as reference, we'll start with the screen backlight.


```shell
sudo sh -c 'echo 2 > /sys/class/leds/tpacpi::kbd_backlight/brightness'
```

Note that I was able to set the maximum. I knew the value 2 to be the maximum after consulting the following file:

```shell
/sys/class/leds/tpacpi::kbd_backlight/max_brightness
```

To change my screen brightness, I'm editing the following:

```shell
sudo sh -c 'echo 1500 > /sys/class/backlight/intel_backlight/brightness'
```
This time I went with something a little lower than the maximum setting.
Again, the maximum value can be found here:

```shell
/sys/class/backlight/intel_backlight/max_brightness
```

Note, it's always a good idea to backup your config files before altering it.
In addition, before running the previous commands, always be sure to consult the original file first. 

