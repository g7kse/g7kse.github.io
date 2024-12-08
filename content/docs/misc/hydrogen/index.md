---
title: Hydrogen gas
date: 2024-12-01
description: How much hydrogen gas do I need to decarbonise
author: Alex
type: docs
prev: /grid
next: /osm
tags:
    - uk
    - grid
    - electricity
    - carbon
---

How much hydrogen do I need in my pipe for there to be any meaningful reduction in green house gases (GHG's)


````mermaid
---
config:
    xyChart:
        width: 900
        height: 600
    themeVariables:
        xyChart:
            titleColor: "#ff0000"
---
xychart-beta
    title "% Hydrogen v Carbon reduction"
    x-axis [0,5,10,15,20,25,30,35,40,45,50,55,60,65,70,75,80,85,90,95,100]
    y-axis "CO2e reduction(in %)" 0 --> 100
    bar [0,1.6,3.2,5,7,9.5,11.4,14,16.7,19.8,23.2,26.9,31.1,35.9,41.3,47.5,54.7,63.1,73.1,85.1,100]
```
