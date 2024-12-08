---
title: Meshtastic Bulletin Board
date: 2023-11-29
description: Cool bulletin board software for Meshtastic
author: Alex
type: docs
prev: /lora_aprs
next: /meshtastic
tags:
    - LoRa
    - packet
    - bbs
    - meshtastic
---

What can I say? who doesn't like a BBS. Ideally its the full AX25 brrrp variety but hey, you can evolve can't you? I've mentioned that I've got a few Meshtastic nodes and I also mentioned that I have a BBS on one of them. So here is a bit of a rundown on how its all working.

### Hardware

Pretty simple really. I wanted to run it off a RPi Zero W that I had loafing about. But for reasons below I'll now say that its running on a RPi 3b. The other thing is a Heltec V3. Thats it!

### Software

I am an occasional viewer of the YouTubes (I guess its plural because there is more that one tube). On a rainy weekend afternoon I was losing hours to the time sucker (TM) and I came across [The Comms Channel](https://www.youtube.com/@The_Comms_Channel) and the video below caught my eye...

{{< youtube 4LuVoDQY-Kc >}}

I had a go and it was pretty simple to setup. But, there are a few buts....

1. Using a hostname didn't work. Maybe this will get fixed in later versions and isn't exactly a priotity or deal breaker
2. Not all cables are the same, the RPi Zero W didn't seem to get on with the Heltec V3 via USB. It just couldn't see it. I suspect it has something to do with OTG, so have parked the Zero route for now.

### How does it work?

Dead simple...Send a message that says "Hello" to the BBS (without the quotes) and you'll get into the BBS, use the menus to navigate and all should be well