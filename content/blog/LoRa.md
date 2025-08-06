---
title: LoRa
date: 2025-01-13
authors:
  - name: alex
    link: https://github.com/g7kse
    image: https://avatars.githubusercontent.com/u/13124178?v=4
tags:
  - APRS
  - Meshtastic
  - LoRa
excludeSearch: true
---

For a little while now I've been mucking about with LoRa devices. These modules come in all sorts of varieties but all have a few things in common. A microcontroller and at least a LoRa module. Quite a few are ESP32 based with SX... LoRa modules and other are nRF... modules. Basically they are really similar and they seem to be an offshoot of IoT devices. But....and here's the useful bit. There are 433MHz versions as well as 868MHz versions.

So the 433MHz versions are ideal for [APRS](https://lora.ham-radio-op.net) and the 868MHz for [Meshtastic](https://meshtastic.org/). 

But the 100mW isn't going to get you very far is it? Well, see for yourself. LoRa is way more effective in practical terms than your usual handheld and experience so far is that the devices are very reliable and cheap. For example, with APRS, a £15 module with a 18650 that lasts all day v a £350+ handheld means that it is also way more accessible. As I get more practical experince with the devices I'll be able to tell how much better they are.

Adding in flexibility is the key for me. My own Meshtastic devices are connected to a local server via MQTT and also run a [BBS](https://github.com/SpudGunMan/meshing-around) and similar functionality is starting to come through with APRS, using the slightly less feature rich [TC2-BBS](https://github.com/TheCommsChannel/TC2-APRS-BBS). These additions are really starting to make the networks more up to date and offer other options for users.

Looking forward to seeing how all this develops.