---
title: LA1
date: 2025-08-01
description: The LoRa APRS 1 - A simple encloser for a Heltec LoRa Tracker
author: Alex
type: docs
prev: docs/coding
next: docs/maidenhead
tags:
  - design
  - LoRa
  - APRS
---

{{< callout type="warning" >}}
 Work In Progress...design needs tidying before its fit to be shown :-)
{{< /callout >}}

## Design Idea
The idea is not exactly new. Create an enclosure to house a battery, a Heltec LoRa tracker and a switch to turn it on and off. Some other bits can be added like a SMA antenna connector and a belt clip if necessary but the basic design should be able to keep as much moisture out as possible (but not water resistant) and for it to have some degree of impact protection should I drop it on a rock, or something like that when out walking.

Now we go from idea to must haves and nice to haves.

| Must / Need | What?                                                      | Note                                                                                                              | Achievable |
|-------------|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|:----------:|
| Must #1     | Impact protection                                          | Be able to withstand a reasonable drop from 1.5m                                                                  |     Yes    |
| Must #2     | Have enough water and dust protection without stopping GPS | No need for an IP style rating just cover the majority of the device but also make it accessible to clean or dry  |     Yes    |
| Must #3     | Be able to be charged up without opening                   | Access to charging using USB C on tracker                                                                         | Yes        |
| Nice #1     | Have common parts or style                                 | Can be used with other LoRa devices with minimal adjustments                                                      |     Yes    |