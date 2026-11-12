---
title: SDRBerry
date: 2026-12-06
authors:
  - name: alex
    link: https://github.com/g7kse
    image: https://avatars.githubusercontent.com/u/13124178?v=4
tags:
  - SDR
  - rig
  - 3D printing
---
[SDRBerry](https://github.com/paulh002/sdrberry) uses a Raspberry Pi and a software defined radio to make a neat looking package. I've got a Raspberry Pi, and an SDR and a 7" touch screen so whats stopping me...apart from time being the obvious one.

Getting the software onto the RPi is pretty straightforward. There is an installation script taht does all the heavy lifting

```
wget https://github.com/paulh002/sdrberry/blob/sdrberry_wayland/install/install.sh
chmod +x install.sh
./install.sh XXX
```
Where XXX is the 3 letters corresponding to your SDR hardware. It takes a while and its a genuine cup of tea type installation. It tooke several minutes on my RPi4 so I actually had a cup of tea and came back when it was done.

There is a config file `sdrberry_settings.cfg` that has all the compenents that need to be adjusted and also a companion application calle [Cat Encoder](https://github.com/paulh002/Catencoder) that can be used with an optical encoder (cheapo one from AliExpress does the job) and you've got a twiddly wheel for tuning around the dial. 

I'll be designing and enclosure for mine over the next few weeks if time allows. The plan is to get a protoype done in time for the new year and maybe SAQ