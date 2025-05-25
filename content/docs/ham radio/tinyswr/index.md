---
title: TinySWR
date: 2024-04-10
description: A pretty small SWR meter - glasses on!
author: Alex Hill
type: docs
prev: /sota
next: /sota_ant
tags:
  - build
  - SWR
---


Martin Hepp has done us a favour and made a [tiny little SWR meter](https://github.com/mfhepp/tinyswr). I had planned on ordering one through Hamshop.cz but noticed that its closed down now. So off to [OSH park](https://oshpark.com/shared_projects/JtKPis3T) for some PCB's. A couple of quid and few weeks later they arrived in the post. Seeing as this is just a little project I'm never that fussed about waiting for stuff to come in the post if its buttons to get something sent. Which it is with OSH Park.

PCB's have arrived and I've updated the [project BOM](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=CA9A31B05C) that was on mouser as a few parts have become obsolete. Feel free to use. I didn't add in connectors or dummy load resistors to the BOM as I thought they should be up to the builder to decide. So onto building it.

### PCB build

Firstly the PCB is pretty small, and the components themselves are tiny. But as I had enough for 3 kits the first was going to be a trial anyway. The instructions are pretty straightforward from Martin's [Repo](https://github.com/mfhepp/tinyswr). I've reproduced them below just to help.

1. Wind the coil. I used some left over coil wire that was 0.2mm for the 25 turns and 0.5mm for the primary. I didn't struggle in getting the enamle off but there's some advise to perhaps use a different type for the primary if you want

2. Install the 0805 parts. My method for this is to flux first, add a small blob of solder to one pad then locate the part on that pad. then solder the opposite and repeat for the first if it looks a little short on solder.

3. Add the trimmer and everything else bar the big LED's. Take care with these items they can be fiddly, especially to get round the right way. If you get it wrong. Don't panic. Use a solder sucker and/or some braid to remove the part and re-orientate. They can be a bit hard to see. In one case I used my reading glasses and a pair of magnifying glasses to get it right. Younger eyes will find it easier :-)

### Putting it together

Putting the PCB into something that is useable is a bit of personal taste. The way that O built the PCB meant that it was always going to be a bit of a faff putting it all together. But I spalshed out on some Amphenol BNC's. One [male] (https://www.mouser.co.uk/ProductDetail/Amphenol-RF/112420?qs=1K%2FD%252BSl2CTOLNb0ei7RBhA%3D%3D) and one [female](https://www.mouser.co.uk/ProductDetail/Amphenol-RF/031-221-RFX?qs=VT5nbRQnyKuxG2JZp560oA%3D%3D) for either end of the case which is in my usual [OnShape](https://cad.onshape.com/documents/25a7a58303e5026c50307cd4/w/ebefe86fd32db31f32a9281f/e/fa13cd15473f041620c5da2e) for 3D CAD

![TinySWR case CAD drawing](/img/tinyswr_cad.png#centre)

Before its all assembled, make sure it works, and works correctly. The small trimmer is there to make sure its not reading too high or low. Mine needed a little adjustment, so that the Yellow LED indicates that RF is flowing and the first red LED just about lights up as it tends towards an SWR of 1.5:1. I wish I had some proper calibration standards for this stuff to be honest. I did have some but they went to a better home as I didn't really use them, kind of regret it now.

Anyway the final build is a little fiddly but here it is, in all its finished glory

![TinySWR in case with bottom off](/img/tinyswr1.jpg#centre)

![TinySWR in case complete](/img/tinyswr2.jpg#centre)
