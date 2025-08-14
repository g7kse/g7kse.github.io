---
title: Raspberry Pi console
date: 2024-10-01
description: A desktop screen for commonly used tools
author: Alex
type: docs
prev:
next: 
tags:
  - Raspberry Pi
  - console
  - RPI
---


Displaying data is a bit of a pain. It can be a job in itself and I've wrestled with this for a while. As you can tell from my [coding](https://g7kse.co.uk/docs/coding/) I'm not exactly skilled in this area. But there are things that i want to show on the desktop without having a second massive screen on the desk. Its not a look I'm after. 

So I bought a Raspberry Pi and a [Touch 2](https://www.raspberrypi.com/products/touch-display-2/) screen and as I run a dashboard application called [Heimdall](https://heimdall.site/) on my server I thought i'd start there. My dashboard is pretty basic. To make sure the links are suitable for a basic touchscreen

![console dashboard](/img/console_front.png#centre)

Ok so its seemingly not that hard to make a rudimentary page that will load in full kiosk mode using a browser. So attempting to find and manage an application, or devise something myself isn't going to be on teh priority list. Adding a new web service is pretty simple. But I'd like to show the [HamTool](https://g7kse.co.uk/docs/coding/hamtool/) as an application might need a bit more effort. I quite like the console but integrating something like that isn't going to be easy for me.

The Touch 2 is a 7" screen and various 3d printable designs exist but they aren't for me. There are some commercially available cases but again nothing quite fitted with the look i was looking for. So I'll design my own, use 3d printing to validate the design and test out ideas before committing to another material or to get something professionally manufactured. The image below is a simple design to get me started. But I found out that not all screens are equal. 

The problem - The screen isn't totally flat. This means that the screen isn't perfectly flush with the case. So it looks rubbish. It looks like the quick fix below isn't in the offing and I'll need to think about this a bit more carefully. 

![Raspberry Pi console case](/img/console_test.png#centre)

---

So, what's the plan. The [C1](https://g7kse.co.uk/docs/design/c1/) is the project and I'll be going through the design of the case in more detail there. The software will no doubt develop and I'll pop any updates on that here.