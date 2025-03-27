---
title: Meshtastic
date: 2023-11-29
description: Meshtastic decentralised messaging network
author: Alex
type: docs
prev: /lora_aprs
next: /meshBBS
tags:
    - LoRa
    - packet
    - bbs
    - meshtastic
---

Like everyone else I have jumped on the [Meshtatsic](https://meshtastic.org/) bandwagon. I think its pretty addictive but one of the thinsg I have noticed is that there isn't actually much chat going on. There are loads of nodes but its like someone is waiting for someone lese to speak (a bit like VHF or UHF repeaters) a few Kerchunk equivalents and "testing" messages but not much else. 

I have 3 nodes. One that is a solar powered RAK version connected to a cheapo AliExpress yagi, a s2nd that acts as the BBS and a 3rd that is one that I use to talk to the others, the latter two are Heltec V3 and T114 respectively. Seeing as the moduels don't cost much and teh yagi was less that £15 delivered then its not a massive investment.

One thing I have done is connect the T114 and V3 to a local [MQTT service](https://cumbriacq.com/meshtastic/) run by Lee, M0LLC who does a lot to connect Cumbria via repeaters and all sorts of weird and wonderful methods. I now have better coverage and can talk to other nodes in the area. Although the number of messages remains low. in fact Lee and I have had longer chats over the equipment setup. This just extends the Ham Radio motto of 

> "People sitting in rooms, talking to other people, sometimes far away, in rooms about the equipment they are using to talk with"

I'm sure there is a better way of explaining it but that'll do for now.

## What is it really?

Meshtastic is a mesh network system that allows you to connect to other nodes and communicate with them. It uses a combination of LoRaWAN and Wi-Fi to provide a simple and semi-reliable system. If you live in the UK then you're not normally too far away from mobile phone coverage and it is unlikley that 'comms' will go down in such a way that it is a problem. So, for us it is more of a hobby and a way to get involved in the amateur radio community. Think of it as a gateway drug to Ham Radio.

Plus LoRa is getting used for APRS so its good to get on board.

### Frequencies and things like that

1. UK is 868MHz, don't bother with 433MHz because you won't hear a thing. believe me I tried it. Save the 433MHz stuff for APRS

2. The stock antennas are rubbish, even the bigger omnidirectional ones aren't great. Cheapo Yagis are good to get a few nodes listed.

3. nRF can be powered by solar. But it needs a much bigger panel than you might think in the UK. My 5w one works ok in the summer but doesn't cut it in the winter, so a boost charge is needed.

4. Consider a BBS. More on that later.

