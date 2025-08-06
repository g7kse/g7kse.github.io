---
title: Server
date: 2024-01-01
description: my home server escapades
author: Alex
type: docs
prev:
next: 
tags:
  - DietPi
  - Home server
  - RPI
---

I have a small home server. It isn't critical infrastructure but it does allow me to do a few things I might otherwise not have been able to do easily. At th eheart of it is a Raspberry Pi 4. The Pi is a few years old but has run for ages without a hitch really. So here is a run down on how it works and what is in it.

### Server Software

![DietPi logo](https://dietpi.com/images/dietpi-logo_240x80.png)

There are many different ways of running a RPi server. My choice is to use the [DietPi](https://dietpi.com) distro. It is rock solid and has been my preference for a few years. Setting up is straightforward, just need a screen and keyboard and then to follow th on screen prompts for things like WiFi details and changing default login details and within about 30 minutes you should be good to go. Most of the time is spent updating everything after the intial first run. So no need to run the usual

``` sudo apt get update && upgrade ```

Everything else is managed headless, so you can ditch the screen if you want (or just use it for this occasion). To access the Pi you can use SSH. You need a couple of bits of infomration. 

1. The IP address of the RPi - Either look this up on your router or if you've got the screen still attached it will say it in the text on the screen
2. The password you probably changed in the setup process

From your favourite Terminal application type the following

``` ssh root@<the ip address of your RPi>```

Then follow the on screen prompts to get access. Once in there are some things that I'd recommend to do. Set up a drive (A USB stick is fine or if you have some external storage that works too, either SMB or NFS). And set up a backup. then set up a back up. Did I mention set up a back up :-)

To access these features type

``` dietpi-launcher```

1. Drive - You'll want to use the Drive Manager for this. Its pretty straightforward but sometimes connecting to external drives can be a bit hit and miss. 
2. Back up - Set up the back up to the drive you just mounted. Check that it works by backing up now

Once this is done the main place to go to is the dietpi-launcher menu. From there slect >Browse Software and a long list of available options exist for pre configured software. These should be the way you install stuff by default, Docker is another option but you'll find support is better with the default methods. Some stuff just isn't there so you have to ude Docker, but you're on your own from there on.

### Applications

A quick note of caution. the stiff on the >Browse Software list generally doesn't conflict. There may be times when you install stuff that can cause a conflict. I have found this to be the case with Web servers and in particularly I got in a mess with Nginx Proxy Manager and spent a bit of time tracking down the reason. Be careful and use the defaults unless you really can't

My server does a few things, you shouldn't really follow my list unless you want to, this is just an illustrattion.

1. [Portainer](https://dietpi.com/docs/software/programming/#portainer) - Graphical Container Manager software
2. [Docker](https://dietpi.com/docs/software/programming/#docker) - A container manager
3. [Nginx Proxy Manager](https://pimylifeup.com/raspberry-pi-nginx-proxy-manager/) - A reverse proxy to get stuff from outside the home network
4. [Speedtracker](https://pimylifeup.com/docker-internet-speedtest-tracker/) - An internet speed tracker
5. [Nextcloud](https://dietpi.com/docs/software/cloud/#nextcloud) - A home document management application
6. [Paperless]() - A receipt and important doc storage area
7. [Jellyfin](https://dietpi.com/docs/software/media/#jellyfin) - A way to watch films and list to music, comes with a android app
6. [Wordpress](https://dietpi.com/docs/software/social/#wordpress) - A website CMS that I use to test stuff

My use case includes being able to access this server using a normal URL. This means that I need to configure a few things. Firstly my router needs to allow ports 80 and 443 to be open for the server. For me this was a simple port forwarding rule on the router software. It also means that I have a domain and that I can set up records on that domain host to point to various things ad sub domains. for exmaple:

next.urlexample.com is a record on my domain and it points to the static IP address I have. Ndinx Proxy Manager then sees that and point to the internal URL (IPaddress:port ). This give me some protection and makes things look better from the outside at th every least. it could be a bag of nails underneath it btw

I would recommend spending a bit of time reseraching the Nginx Proxy Manager before doing this. it isn't as hard as it sounds once you've given it a go but a tutorial will help if you get stuck

To get access to the Pi Hosted templated use this in the portainer templates settings 

  https://raw.githubusercontent.com/pi-hosted/pi-hosted/master/template/portainer-v2-arm64.json 

### Add ons

#### Screen

Adding a screen to give you a few stats on your server is pretty easy. the only thing to worry about is making sure that you have the right OLED. Using the [MKlements](https://github.com/mklements/OLED_Stats) Repo should help.

I've added one and its pretty straightforward. If you hook it up and your screen is covered in teh mush then its the wrong screen type. Soz

#### Enclosure

I promise, one day I'll put it in a box, there are just too many other things to do. Sound familiar. The main reason is that I want to have a PCB that does the power stuff as well. Just not got round to it. Maybe in ~~2024~~ 2025 :-)