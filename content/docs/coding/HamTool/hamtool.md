---
title: HamDash
date: 2024-09-28
description: A work in progress for an ePaper display of funky ham radio stats
author: Alex
type: docs
prev: docs/coding
next: docs/maidenhead
tags:
  - python
  - ham radio
  - coding
---
HamTool is a simple application - Its nothing special and I'm sure the way its done could be done better. But, its something that wasn't there before as far as I can tell. The main emphasis is....

1.    The command line is pretty good looking (I use Ubuntu but am no great Linux guru, just a casual user)
2.    Lets use the command line more because its probably more efficient

Note: I am not a code, developer, programmer or anything like that. It should be evident from the state of the code

### Basis of design

There are short scripts that are called by a main menu. Each script runs in a new Terminal tab and is therefore independent of the menu. there's no limit to the tasks and its probably sensible to bundle a few together, especially if they are starting applications. I thought initially that 9 would be a sensible limit as they are single numbers with 0 being the number for 'Exit'

I don't really know a language but python seemed like a sensible option to try. There will be bits of code nicked from all over the place. At one point I used some AI to look at errors I was getting and couldn't find an answer to easily. Those bits of code should be obvious to the accomplished developer.

### Why do this?

Well the DJ5CW 52 Week ham Radio Challenge has a section for "write a useful ham radio programme" with the helper being...

The program can be built in any programming language, written or graphical. If you have never programmed before, here are some ideas of what your program could do: Calculate the length of a dipole for a given frequency. Look up which Amateur radio band a frequency belongs to, if any. Convert a letter to its representation in the ICAO alphabet (Alpha, Beta, ...) In order to get started quickly, here are some websites where you can write and run code immediately, without the need to install anything: Go: Go Playground

I think this might qualify once its done. Well I hope it is :-)