---
layout: post
title: "How-to select audio output source via PipeWire. (Fedora 36)"
categories: linux, hardware, fedora
---

Run the following to retrieve the sate of your devices

```shell
wpclt status
```

You should have an output like this. **if you notice some empty results, run the command again.**

```shell
PipeWire 'pipewire-0' [0.3.56, phantom@fedora, cookie:2650888390]
 └─ Clients:
        32. WirePlumber                         [0.3.56, phantom@fedora,
            pid:1422]
        33. WirePlumber [export]                [0.3.56, phantom@fedora,
            pid:1422]
        59. wpctl                               [0.3.56, phantom@fedora,
            pid:1474]

Audio
 ├─ Devices:
 │      38. Pixel earbuds                       [alsa]
 │      39. Built-in Audio                      [alsa]
 │
 ├─ Sinks:
 │  *   44. Pixel earbuds Analog Stereo         [vol: 0.74]
 │      46. Built-in Audio Analog Stereo        [vol: 1.00]
 │
 ├─ Sink endpoints:
 │
 ├─ Sources:
 │  *   45. Pixel earbuds Mono                  [vol: 0.74]
 │      47. Built-in Audio Analog Stereo        [vol: 0.74]
 │
 ├─ Source endpoints:
 │
 └─ Streams:

```

Now you can modify the output device as follows. **Note by choosing 46, it will place set the default Sink to 'Built-in Audio Analog Stereo'**
```shell
wpclt set-default 46
```
