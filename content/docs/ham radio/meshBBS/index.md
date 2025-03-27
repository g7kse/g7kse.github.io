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

It turns out that [Meshtastic](https://meshtastic.org/) offers a way to bring a bit of that nostalgia back. Several options exist as far as I can tell. One is by The Comms Channel, which incidentally had a go at an APRS version, and the other by SpudGunMan. Both have similar BBS functionality but the SpudGunMan version has more options, but also more to go wrong.

### Software

I'm not going to look at every available option but I think there are art least 2 that I can find. The TC2 version and the SpudGunMan version. There are probably more but for now I think these 2 options are th emost useful to look at

**Option 1 - TC2 Mesh BBS** 

I am an occasional viewer of the YouTubes (I guess its plural because there is more that one tube). On a rainy weekend afternoon I was losing hours to the time sucker (TM) and I came across [The Comms Channel](https://www.youtube.com/@The_Comms_Channel) and the video below caught my eye...

{{< youtube 4LuVoDQY-Kc >}}

I had a go and it was pretty simple to setup. But, there are a few buts....

1. Using a hostname didn't work. Maybe this will get fixed in later versions and isn't exactly a priotity or deal breaker
2. Not all cables are the same, the RPi Zero W didn't seem to get on with the Heltec V3 via USB. It just couldn't see it. I suspect it has something to do with OTG, so have parked the Zero route for now.

So, lets be completely clear. there is nothing wrong with the software as far as i can tell. For me the setup wasn't quite what I wanted but there is no reason to suggest that it isn't for you. As of today my advice is to use a proper RPi or find a cable that works for you if you want to go with a wired solution, or wait until the Hostname feature is fixed and connect via that route (which seems like the most flexible option to me).

Have a look on the [Github](https://github.com/TheCommsChannel/TC2-BBS-mesh) to see how it is developing

**Option 2 - Meshing Around**

I have no idea how I came across this but that doesn't matter. This has a few more features than the TC2 version **but** they don't all seem to work. 

1. Some of the more potentially useful features like schedulling and emergency messages don't work in the UK and have been removed. They might work for you but keep this in mind. 
2. There is also a feature for LLM interaction but this was painfully slow on the RPi 4 that runs my little server. Responses were somewhere between 60 & 90 seconds. Which make them unusable as far as I am concerned. I might upgrade the server at some point to one of the more powerful thin client types but for now the RPi does most of what I want.

Again these are bits of hobby software so it is unreasonable to expect that you're getting corporate level stuff. Some of the fixes are there but I'm not going to hammer some guy who I've never met to fix something. If the developer is keen to do so then its over to them. Occasionally I can do the fix but its not common.

Here is a link to [SpudGunMan's Meshing Around](https://github.com/SpudGunMan/meshing-around) effort. Well worth looking at


### Current setup

After a bit of trial and error I have setted on [Meshing Around](https://github.com/SpudGunMan/meshing-around). I have a [Heltec E213 EInk LoRa node](https://heltec.org/project/vision-master-e213/) called BBS. This is conencted to the RPi through my local network using its Hostname. Access to it is really simple, it currently works through direct messaging but there may be a call to set up a specific channel but I can see problems with this tbh. Who wants to see 101 messages every time they connect rather than the ones that refer to themselves?

**Commands**

I've taken the list from the github readme and removed th efeatures that I have currently diabled. There is quite a lot that aren't shown by the `cmd` function as you can see

#### Networking
| Command | Description | ✅ Works Off-Grid |
|---------|-------------|-
| `ping`, `ack` | Return data for signal. Example: `ping 15 #DrivingI5` (activates auto-ping every 20 seconds for count 15) | ✅ |
| `cmd` | Returns the list of commands (the help message) | ✅ |
| `history` | Returns the last commands run by user(s) | ✅ |
| `lheard` | Returns the last 5 heard nodes with SNR. Can also use `sitrep` | ✅ |
| `motd` | Displays the message of the day or sets it. Example: `motd $New Message Of the day` | ✅ |
| `sysinfo` | Returns the bot node telemetry info | ✅ |
| `test` | used to test the limits of data transfer `test 4` sends data to the maxBuffer limit (default 220) | ✅ |
| `whereami` | Returns the address of the sender's location if known |
| `whoami` | Returns details of the node asking, also returned when position exchanged 📍 | ✅ |
| `whois` | Returns details known about node, more data with bbsadmin node | ✅ |

#### Radio Propagation & Weather Forcasting
| Command | Description | ✅ Works Off-Grid |
|---------|-------------|-------------------
| `hfcond` | Returns a table of HF solar conditions | |
| `rlist` | Returns a table of nearby repeaters from RepeaterBook | |
| `solar` | Gives an idea of the x-ray flux | |
| `sun` and `moon` | Return info on rise and set local time | ✅ |
| `wx` and `wxc` | Return local weather forecast (wxc is metric value), NOAA or Open Meteo for weather forecasting | |

#### Bulletin Board & Mail
| Command | Description | ✅ Works Off-Grid |
|---------|-------------|-
| `bbshelp` | Returns the following help message | ✅ |
| `bbslist` | Lists the messages by ID and subject | ✅ |
| `bbsread` | Reads a message. Example: `bbsread #1` | ✅ |
| `bbspost` | Posts a message to the public board or sends a DM(Mail) Examples: `bbspost $subject #message`, `bbspost @nodeNumber #message`, `bbspost @nodeShortName #message` | ✅ |
| `bbsdelete` | Deletes a message. Example: `bbsdelete #4` | ✅ |
| `bbsinfo` | Provides stats on BBS delivery and messages (sysop) | ✅ |
| `bbslink` | Links Bulletin Messages between BBS Systems | ✅ |

#### Data Lookup 
| Command | Description | ✅ Works Off-Grid |
|---------|-------------|-
| `messages` | Replays the last messages heard, like Store and Forward | ✅ |
| `readnews` | returns the contents of a file (news.txt, by default) via the chunker on air | ✅ |
| `wiki:` | Searches Wikipedia and returns the first few sentences of the first result if a match. Example: `wiki: lora radio` |

#### CheckList
| Command | Description | ✅ Works Off-Grid |
|---------|-------------|-
| `checkin` | Check in the node to the checklist database, you can add a note like `checkin ICO` or `checkin radio4` | ✅ |
| `checkout` | Checkout the node in the checklist database, checkout all from node | ✅ |
| `checklist` | Display the checklist database, with note | ✅ |

#### Games (via DM)
| Command | Description | ✅ Works Off-Grid |
|---------|-------------|-
| `blackjack` | Plays Blackjack (Casino 21) | ✅ |
| `dopewars` | Plays the classic drug trader game | ✅ |
| `golfsim` | Plays a 9-hole Golf Simulator | ✅ |
| `hamtest` | FCC/ARRL Quiz `hamtest general` or `hamtest extra` and `score` | ✅ |
| `hangman` | Plays the classic word guess game | ✅ |
| `joke` | Tells a joke | ✅ |
| `lemonstand` | Plays the classic Lemonade Stand finance game | ✅ |
| `mastermind` | Plays the classic code-breaking game | ✅ |
| `videopoker` | Plays basic 5-card hold Video Poker | ✅ |

### Web Interface

There is a web interface available through a local web server that I've not investigated thoughly yet