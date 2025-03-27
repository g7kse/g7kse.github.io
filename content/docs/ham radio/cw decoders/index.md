---
title: CW decoders
date: 2024-09-28
description: Fun with 13cm
author: Alex
type: docs
prev: docs/radio
next: docs/sota
tags:
  - CW
  - CW Academy
  - Morse
  - Decoder
---

### Introduction

There’s no doubt about it. Learning CW fully is the way to go. How you go about doing it is well documented and whether the Koch or Farnsworth method suits you is almost entirely down to personal preference. I would always recommend the [CW Academy](https://cwops.org) as a place to learn in a group. Their programme is excellent and if you have the time and patience, they will take you to 25 words a minute in a structured way. But, and here’s the big but, not everyone can ride in the Tour de France, some people like to ride slower and others need to use an e-bike to get up those big alpine climbs. Should they be excluded? Not in my world.

So, if CW decoders exist, why not build one? At worst it can show how the Mk 1 earhole is better than the electotrickery of a microcontroller. At best it is going to bring another CW operator into the fold, albeit with a crutch (Yes, I am fully aware that purists scoff at these devices, but frankly I’m not bothered)

### So, how can one cheat?

Well, there’s more than one way to skin this particular cat. But over the last few years as Arduino type microcontrollers have grown and developed, so has the sophistication. There are options for phones as well. So here’s a run down of this controversial subject with a selection rather than an exhaustive list. Lets tackle the subject head on with a really good decoder for your phone, made by the dude who brought your CW Skimmer Alex Sjovkopolis, VE3NA. Morse Expert is for your phone (Let me throw this in… imagine the irony of a community that relies on CW decoders to aide operation in one way but not another 😊). Other decoders exist for your phone, you choose if you want to search for one for Android or fruit based product. However this isn’t the point of this document.

### Microcontrollers

|   Name                                                                                                                                    |   Platform          |   Notes                                                                                                                                                                                                                    |   |   |
|-------------------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
|   [K3NG Keyer](https://radioartisan.com)                                                                                                  |   Arduino & others  |   Probably  the best known CW Keyer  for the homebrewer. It is described as a swiss  army knife (and who am I to argue). It includes a decoder based on the  Goertzle method. Keep this  in mind as it appears elsewhere.  |   |   |
|   Shovkholm                                                                                                                               |   Arduino           |   The  defacto standard for Arduino decoder. This method crops up all over the  place with tweaks and advances, but this is the original as far as I  can tell                                                             |   |   |
|   Shovkolm variant (LCD)                                                                                                                  |   Arduino           |   A variation with a tuning aid. The original article seems to have been removed but the software is here                                                                                                                  |   |   |
|   Shovkolm variant (SSD 1306)                                                                                                             |   Arduino           |   A further variant without tuning aid but using a smaller SD1306 OLED screen                                                                                                                                              |   |   |
|   Jim Harvey                                                                                                                              |   All sorts         |   A  whole heap of different developments that include a CW keyer with  Bluetooth keyboard. Really Smart and one to try in the future                                                                                      |   |   |
|   Morserino                                                                                                                               |   Arduino           |   Using a different software approach with a hardware tone decoder                                                                                                                                                         |   |   |
|                                                                                                                                           |   Teensey           |                                                                                                                                                                                                                            |   |   |
|   [G6EJD]( GitHub - G6EJD/ESP32-Morse-Decoder: Using an ESP32 and OLED with a basic microphone to decode Morse Code live to the display)  |   ESP32             |   Uses an ssd1306                                                                                                                                                                                                          |   |   |

### Which ones have I built?

Well not many, so experience is limited, although I am keen on them as a little bit of fun