---
title: A kindle as a TrmNL?
date: 2026-05-12
authors:
  - name: alex
    link: https://github.com/g7kse
    image: https://avatars.githubusercontent.com/u/13124178?v=4
tags:
  - ePaper
  - kindle
  - technology
excludeSearch: true
---

I've been hankering after a [TRMNL](https://trmnl.com/) for a little while but never got round to getting one. Other stuff got in the way. I also owned a Nook ereader a while ago, but that went to the great ewaste container in the sky. So here's me search the house for an ereader because I had found a couple of ebooks to read. I found 2. A really old Kindle, the ones with the keyboards and an original kindle touch (7th generation).

So, the kindle with a keyboard and page turning buttons became the one I read the book on. The other was ripe for farting around with. What I actually mean to say is wasting hours of time on. So here's the plan...

✅ Jailbreak it  
✅ See if I can muster a crappy little application for it  
✅ Spend hours 'researching' (see also going doing interwebrabbitnetholes)  
✅ Turn it into a tighwads TRMNL  

Mission accomplished! End of post ☺️

### What did I do?

There are plenty of sites that tell you how to Jailbreak these things. The crucial this is to know what the serial number is so you can confirm the model, so it'll ]give you have a chance of completing the job before you draw your pension

1. [Kindle Modding](https://kindlemodding.org/jailbreaking/) was the guide I used
2. Find out your model from [this webiste](https://en.bookfere.com/post/kindle-serial-number-lookup-model-identification.html)
3. The Kindles MAC address - Handy later but not crucial

Give yourself a good few hours - whilst all the steps seemed to work, when I got to one of the crucial parts something wasn't right with my install and it all went in circles. Lots of circles. Just follow the guide and eventually it 'should' work.

Next up things started to go all techtastic. I have a server of sorts, its just a Raspberry Pi running [Dietpi](https://dietpi.com/). But I've set it up with Docker and Portainer. I half know what I'm doing if the job is pretty painless. 

So I logged into Portainer and created a new Stack abd used the Docker script thing for the [LaraPaper](https://github.com/usetrmnl/larapaper). I tried Terminus (the TRMNL default server) but it really didn't work for me. Maybe it was my machine but several hours were gone trying to fix stuff. Binned it!

The Docker script has a crucial extra bit. Teh site didn't render correctly for me so the ENVIRONMENT VARIABLE ```FORCE_HTTPS=1``` needed to be added

```yaml
services:
    app:
        image: ghcr.io/usetrmnl/larapaper:latest
        ports:
            - "4567:8080"
        environment:
            # Generate the APP_KEY with `echo "base64:$(openssl rand -base64 32)"`
            - APP_KEY=base64:YOUR KEY HERE=
            # Base URL of the application
            - APP_URL=YOUR URL HERE
            - FORCE_HTTPS=1
            - PHP_OPCACHE_ENABLE=1
            - TRMNL_PROXY_REFRESH_MINUTES=15
            - DB_DATABASE=database/storage/database.sqlite
        volumes:
            - database:/var/www/html/database/storage
            - storage:/var/www/html/storage/app/public/images/generated
        restart: unless-stopped
volumes:
    database:
    storage:
```

Once the service is up and running you need to find your sever in the browser ```https//:IP ADDRESS:4567``` should do it. Log yourself in and what I did was turn on "Permit Auto Join" in the top right hand corner. 

Now this bit was a bit of a mystery, before I knew it there were loads of versions of my Kindle in the list. before I did anything else I turned off "Permit Auto Join" then deleted all but the last one.

So in theory your Kindle is on the Larapaper books, but your Larapaper isn't on your kindles books. You've 2 options here that I tried. The first is the [TRMNL kindle extension](https://github.com/usetrmnl/trmnl-kindle). Just couldn't get it to work. After several hours of trying this and that I gave up. perhaps it was a simple fix but I just kept getting JSON errors. So switched my attention to KOReader (which I installed as part of the jailbreak game). There is a [plugin for it](https://github.com/usetrmnl/trmnl-koreader)

*BLAMMO* It worked.

So that left me with some time to muck about and work out what I wanted to see. I guess this took a lot longer than it perhaps could have but easy half day including the farting about. More competent people could take less time. But my shortcuts are...

1. Jailbreak
2. Install KOReader
3. Install LaraPaper in a container
4. Install the KOReader plugin

Enjoy - I spend too long doing stuff so you don't have to 