---
title: HF Packet radio
date: 2026-01-04
authors:
  - name: alex
    link: https://github.com/g7kse
    image: https://avatars.githubusercontent.com/u/13124178?v=4
tags:
  - HF
  - Packet
  - Digital
---

A little christmas project for me has been to have 'proper' go at HF packet. One of the things that was seeming to make it harder that is should was the IC7300 just wouldn't transmit consistently. One day it would work and another day it couldn't be bothered. For posterity here are the setting on QtSoundModem that worked when it was in FT8 "mode".

![QtSoundModem Devices](/img/packet_devices.png#centre)

A few partial and one total reset later and checking all the settings in the connections menu (and on QtSoundModem) and its all working nicely. The only issue with HF is its a bit easily upset by the sun. This, and it is outstandingly slow has been a bit of a pain. But, leaving it for a bit and some traffic appeared.

![QtSoundModem Monitor](/img/packet_monitor.png#centre)

With this all happening nicely I attempted to connected to an EI node that was pretty much un-obscured by land. And to my surprise to connected first time

![QtTermTCP Connect](/img/Ei6IYB.png#centre)

And digging around I get this..an old school news thread. Nice!

![QtTermTCP News](/img/packet_news.png#centre)

So, with a bit of success I started out to specify up anode for myself. A Nino TNC has been ordered from [HamServe](https://www.hamserve.uk/tarpn-ninotnc-n9600a/) and I've started building a LinBPQ based node. At some point I'll pull all this together into a node, probably on 2m, with an attempt to make all this join up with the GI nodes across the Irish Sea. Although it'll probably be a while before it all gets sorted out as LinBPQ seems to be messing me around quite a bit. 