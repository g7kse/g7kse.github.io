---
title: "SOTA Antennas"
date: 2023-11-29
decription: A few antennas that I'm mucking about with for SOTA and /P
author: Alex
type: docs
prev: /sota
next: /wota
tags:
  - radio
  - sota
  - portable
  - summits
  - antenna
  - hf
---

One of the fun things I like to do is experiment with antennas to find a compromise that works for me. Most of the time I'll deploy an End Fed Half Wave (EFHW) antenna for HF. These are pretty simple antennas that are either made for use with or without a tuner. The trouble with them is they need a bit of space and we don't always get that on summits. Another thing I've found is that I don't get much DX with them. So sometimes I like to mess about with other options. Verticals are one of those options.

For VHF the [flowerpot](https://g7kse.co.uk/projects/flowerpot/) is my 'Go to'. I think I've found the best bang for my buck and can't see me changing that in the short term

Quite a lot of my experiments come with 3D printed parts. Some are just PCB antennas like the 13cm one in the main image

Here are a few of my favourite things....

## DK3IT 3 Band

Martin Hepp, DK3IT has made a few things that are worth looking at. His GitHub repository has a handy SWR meter but his take on a 3 band vertical antenna for the 40m, 30m and 20m bands. Guess what, these are handy bands for a lot of SOTA activations and rigs like the Mountain Toppers.

The 3 Band antenna is a simple coil former that sits over a mast with tapping points for the bands. The recipe calls for a few bits and pieces but they are all available on your favourite marketplace that isn't Amazon!

Martin put some detail on the [SOTA Reflector](https://reflector.sota.org.uk/t/sota-vertical-antenna-for-40-30-20m/15673) in 2017 but is wasn't until November 2023 that I picked it up. 

Martins print is pretty robust an uses 2mm push fit (RC car) pin which are easy to come by and easy to work with. The design works for a specific pole so once I've experimented with it I'll make it work for either my SOTABeams Carbon 6 of older fishing pole (thats had many tears of battering)

Martin's STL's are in [Thingiverse](https://www.thingiverse.com/thing:2450117)

#### Shopping list
* 2mm RC plugs - Could only find these on eBay
* 0.65mm enaml copper wire - normal suppliers or eBay
* small croc clips - I had a load of them left over from a previous STEM project used them

## Multiband Ground Plane

I've been tempted by this one for a while but couldn't quite get around to making it. The design is like a lot of verticals with loading coils. Its a long print (about 20 hours on my machine) and a pretty robust model although it lacks a bit of finess on the radiused parts. Ripe for a remix if you ask me. The original design come from [EB5EKT](https://www.youtube.com/watch?v=EyTAq1XbE1k) but was developed and I settled on the [OK1CDJ version](https://www.thingiverse.com/thing:2030237). Ondra has contributed quite a few things and his shop was useful but looks like its shut down.

#### Shopping list
* 1.5mm diameter aluminium wire - eBay 
* M6 A2 (stainless) nuts bolts and washers - Local supplier or eBay if you must
* Antenna wire - The [SOTABeams](https://www.sotabeams.co.uk/rf-cables-cords-and-wires/) stuff is pretty good. Choose your weapon
* Reusable zip ties - Local supplier or eBay if you must
* RF connector (I use BNC's generally for portable stuff)
* M3 nuts and bolts to suit the connector
* Wire for the antenna and some crimp eyes and your choice of heat shrink
* Don't forget a couple of crocodile clips (you can use either 1 or 2 depending on how you want to short the coil)

The print was pretty simple, if not a bit crude in the way it must have gone from CAD to STL, still it all works fine but takes a while to get done so best go and get a good nights kip!

So now you've got the parts. The rest is just a straightforward build, start by winding the coil. Give yourself a decent 'tail' each end so you can fasten in place when you're happy with the way it sits. Try and keep it as tight as you can to the former as that will help later on.

Add the crimp eyes (pro tip - just crimp enough to close the gap and then solder in place) and bolt the coil up. I checked the inductance with my LCR meter. Just for reference this is the value I got was just under 24uH.

![Coil under test](coil1.png#centre)
![Finished coil](coil2.png#centre)

## 10m band Hentenna

Got passed [this](https://hb9sota.ch/wp-content/uploads/2015/07/The-Hentenna-Pr%C3%A4sentation_EN-HAM16.pdf) the other day, looks interesting but not tried it yet. Looks like a useful build for the 2024 10m challenge on SOTA


## A note about carbon masts

I think this sums it up nicely. As always YMMV but I use a carbon 6 mast and its probably my most useful one

{{< youtube idx1zdmeIOs >}}

## Some useful references

Info about verticals thats not too techie from [Practical Antennas](https://practicalantennas.com/designs/verticals/5eights/)