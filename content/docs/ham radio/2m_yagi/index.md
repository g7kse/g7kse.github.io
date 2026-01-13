---
title: 2m yagi
date: 2026-01-13
description: Notes on making a low cost 3 element 2m yagi
author: Alex
type: docs
next: docs/packet
tags:
  - 2m
  - VHF
  - antenna
---

Donkey's years ago [Sotabeams](https://sotabeams.co.uk) used to sell a 2m and 70cm yagi. It was called the SB270. I bought one and its been a really useful antenna for probably 15+ years now. But soon after I bought mine they stopped selling them, just at the time that the club had a few activators for [Wainwirghts on the Air](https://www.wota.org.uk/). With nothing available there was a hole to fill and our local diy chain store and everyone's favourite weekend haunt (B&Q) stocked the right kind of materials to make your own.

From what I could tell at the time, the beam followed pretty much the [DK7ZB Ultralight](https://www.qsl.net/dk7zb/start1.htm) design but with values tweaked to be resonant at 145.500 MHz rather than 144.300 MHz. All the construction materials are roughly the same and the matching unit was, again, very similar. The SB270 used through beam element holders whilst teh DK7ZB used above beam. So that probably has some influence on element dimensions.

Using everyone favourite formulae 

v=f*λ  where v = 299792458 or 3x10^8 m/s depending on how accurate you want to be. We want λ, so re-arranging

λ = 299792458/145500000
  = 2.0604293m

Here's where it gets a bit weird and too precise science for me, but its here anyway. the length of reflector, driven element and director are 0.495λ, 0.473λ and 0.43λ 

This gives us lengths as follows:


Reflector   =   0.495λ * 2.0604 =   0.995m  
Driven      =   0.473λ * 2.0604 =   0.960m  
Director    =   0.430λ * 2.0604 =   0.880m  

Space between driven and reflector  =   0.21λ = 0.21 * 2.0604 = 435mm  
Space between driven and director   =   0.23λ = 0.21 * 2.0604 = 470mm  
Total boom length                   =   905mm  

This is all very convenient as you fit all this into 1 metre long parts. So the maths is one thing the reality might be slightly different. The dimensions of the rods might be a bit different, the material is idealised and frankly not many people can cut rods exactly and without any deviation, the beam material will have an effect. So whilst the maths is here. It is a guide. Fiddling about is mandatory.

So we need some parts.  

For elements the values have been based on 3mm-ish welding rods. This material is pretty easy to get hold of in those lengths, but if you want to make life easy use someone like [Metals4U](https://www.metals4u.co.uk/materials/aluminium/aluminium-round/101840-p) or [Aluminium warehouse](https://www.aluminiumwarehouse.co.uk/collections/aluminium-round-bar). For boom material the test beam used think walled pvc tube from someone like [Screwfix](https://www.screwfix.com/c/heating-plumbing/pipe/cat831500). Thick walled stuff is way better if its going anywhere near outside.

For fitting the elements to the boom. I struggled to get anything off the shelf that was a drilled bolt, either nylon or otherwise. Other options are the standard clips e.g. this from the DK7ZB website (did I mention this was the source of the detail....go there for the original detail and design. There are loads of excellent options there!)

![9A5NLO arrangement on the DK7ZB website](https://www.qsl.net/dk7zb/PVC-Yagis/3-El-9A5NLO.jpg#centre)

My janky design is originally here as presented to the club many years ago....

{{< pdf "/docs/ham-radio/2m_yagi/bnqbeam.pdf" >}}
