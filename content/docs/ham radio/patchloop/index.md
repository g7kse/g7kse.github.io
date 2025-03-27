---
title: Patchloop antenna
date: 2024-04-10
description: An innovative receive loop antenna
author: Alex
type: docs
prev: /morse
next: /saq
tags:
  - antenna
  - loop
  - VLF
  - MW
---

Henning Paul might just have another contender for the SAQ VLF antenna collection. His [PatchLoop](https://github.com/hennichodernich/patchloop) is about as simple as it gets (along th esame lines as the mobius [YouLoop](https://airspy.com/youloop/) design that I managed to destruct a while back).

There's very little to it. An ethernet cable, some plugs, a balun and an SMA connector. Plus the PCB of course. The PCB's can be ordered from anywhere you like. I used JLCPCB and they arrived slowly but cheaply. The other parts can be ordered either through your preferred supplier or alternatively I produced a project [BOM on Mouser](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=70ac9f78de) in case you need it.

Having had very little success with the miniwhip (despite others doing ok with it) I have consigned that to the 'only if I'm deperate' pile. The YouLoop was way better. Other contenders have been various active loops which have all failed in one way or another. Mainly because I was transmitting near them (not into them) at QRP levels during testing and never got round to actually making a comparison.

### Antenna build

Really simple. A bit of water pipe in a loop with a diametr of around 1m was my choice. I could fit 6 turns of Cat 5 inside it after cutting one of the mouled connectors off a long patch lead. All I had to do was terminate the cable (It took way longer than a pro might do it, mainly to keep checking that everything was in the right place. Simple.

![Patchloop](/img/patchloop.jpg#centre)

There is a connection PCB that collects together the ends of the Cat5 cable and ensures that they are in a loop. In my case there are 6 turns of cabbel within the balck tube. it is a bit of a tight fit but it works if you're careful and pull everything tight. No room for any more in there but no reason why the loop couldn't be bigger or the tube thicker!

Here is a close up of the box that I use. Nothing special, just something that was kicking about after I mis ordered for a different project

![Connector box](/img/patchloop_connect.jpg#centre)

And a final close up of the PCB itself. the balun is pretty small but solderable (is this a word?)

![PCB](/img/patchloop_pcb.jpg#centre)

### Performance

As this is a receive antenna I can confidently say that the lower the frequency the better it is compare to my long wire, dipole and mini-whip antennas. I used it for the SAQ Centennial transmission on 1st Decemebr 2024 and it worked really well on VLF and up to MW. Once you get much past 80M then it drops off a bit and the past 40M the long wire and dipoles are better.

Here's the SAQ video. Skip to the end if you want to see how strong MSF and DCF are. Normally much weaker here

{{< youtube 94ESOz2go-c >}}