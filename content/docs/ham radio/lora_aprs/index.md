---
title: LoRa APRS
date: 2023-11-29
description: Inexpensive APRS Tracker & iGate using LoRa modules
author: Alex
type: docs
prev: /meshBBS
next: /meshtastic
tags:
    - LoRa
    - APRS
    - tracker
    - iGate
---

In 2021 I did a STEM project with a school called CANSAT. The project used LoRa modules to transmit data from a model rocket payload and a ground station. I started to get interested in these modules and to cut a long story short have a few of the Lillygo [TBEAM](https://pt.aliexpress.com/item/32967228739.html?gatewayAdapt=glo2bra) versions.

The version I have runs on 433MHz and use the code in the links above. I ended up using this code because of a change in component on my boards that meant some of the other code that is also used wouldn't work and ended up in a boot loop.

As a little toy it's quite fun to see how far 100mW can go but realistically without adding additional components they aren't going to replace my APRS hand held

### Fast forward to now-ish

Since starting to look at this there has been a bit of a mini explosion in this area. The T Beam modules have been overtaken a litlle bit by the [Heltec Tacker](https://heltec.org/project/wireless-tracker/) modules that are a little bit more compact and are slightly better performing. thats not to say that the T Beam is useless, far from it , but the Heltec ones are a bit more polished.

![Heltec Tracker module](https://heltec.org/wp-content/uploads/2023/06/tracker-1.png#centre)

Note: mine is on order so I can't really comment on how good it is but I will as soon as it arrives.

### UK Frequency

There was a bit of 'bedding in' needed with the frequency for APRS in the UK. It has settled on 439.9125 MHz as its out of the way of everything else and less like to cause QRM. The good news is that there has been a relaxing in the tyoe of NoV required for things like digipeaters. So a few solar powered ones are kicking about that make use of the low power requirements. 

[APRS.fi](https://aprs.fi) shows the current crop 

### Software

1. [Richon Guzman](https://github.com/richonguzman/LoRa_APRS_Tracker) - Just use this...just works. Use the web flasher for the simplest method.
