---
title: "Our Network"
date: 2020-09-16T10:30:32-04:00
slug: "our_network"
description: "Our home network setup"
keywords: ["computers", "networks", "IT", "minecraft", "raspberrypi", "odroid", "voip"]
draft: false
tags: ["computers", "networks", "IT", "minecraft", "raspberrypi", "odroid", "voip"]
math: false
toc: true
---

## Our Network
![Our Network](/images/network-diagram.png)
Our home network evolves over time, sometimes significantly. I'm always interested in trying out new things and switching things up if I come up with new ideas.

I'm always playing with DNS settings, the DHCP server, Network Attached Storage and the firewall/router and changing and reconfiguring things as I go. Sometimes I want to try out a new device, sometimes something breaks down and I need to replace it. It's always interesting.

I use a specific IP address range with an unusual netmask just because I can. I guess it might serve to confuse anyone who broke into our network, but probably not.

### Components
Right now we have a 75Mbit/s cable connection from [Netfox](https://www.netfox.ca/) that goes directly into our new, D-Link DIR-1750 wireless router. A Cat6 cable goes back to a gigabit switch (and one computer that is close by) and then the switch is connect to our servers, our VOIP box, the other computer in the room and a powerline transmitter.

The powerline transmitter sends the network signal over the house electrical lines to the basement apartment to connect that to the network. That was a bit expensive, but it's quite reliable.

I also have a D-Link DAP-1530 wireless extender upstairs to make network connections a bit more reliable at the farthest reaches of the house. Because of lockdowns at work due to COVID-19, I've been working at home and this allows me to have a reliable network connection far away from most of our family's daily activity.

## Internet Services

### DNS-O-Matic
I use OpenDNS's [DNS-O-Matic](https://www.dnsomatic.com/) to update our dynamic IP address with a couple of different services, including [no.ip](https://www.noip.com/). That way we can have a reliable network name that points to our current Internet IP address and we don't have to keep track of it and tell friends and family members who want to connect from the Internet whenever it changes.

### Netlify
Nicole and I use [Netlify](https://www.netlify.com/) to host and publish our blog sites. We work on blog posts on our laptops and then commit and push our changes to GitHub. Netlify automatically gets those changes and publishes them. No muss, no fuss ;-)

## Raspberry Pi
![Raspberry Pi Logo](https://nira.ac.in/images/cropped-Raspberry-Pi-Banner.jpg)
One of the fixtures of our network has always been one or more Raspberry Pi computers. Ever since the Raspberry Pi first came out in 2012 I've been using them for various things. I have four of them right now, but not all of them are currently in use.

I purchased a Raspberry Pi 4 with a Flirc case to use as our Minecraft server as soon as they were available.
![Raspberry Pi with Flirc case](https://cdn.shopify.com/s/files/1/0176/3274/products/514B76sMz2L._SL1500_1024x1024.jpg "Isn't it lovely?")
This aluminum case actually connects via a thermal pad to the main chip on the Raspberry Pi board. This makes a solid connection and the whole case acts as a heat sink. No fan required.

### Kodi
![Kodi Logo](https://kodi.tv/sites/default/themes/kodi/logo-sbs.svg)
One of the first uses I had for the first Raspberry Pi I bought was as a set top box connected via HDMI to our TV. The obvious choice for this was some kind of Linux distribution running the [Kodi](https://kodi.tv/) entertainment centre software. Of course someone already had a purpose-build OS for the Pi called [OpenELEC](https://openelec.tv/) (Open **E**mbedded **L**inux **E**ntertainment **C**enter). I used that for awhile and then switch to [LibreELEC](https://libreelec.tv/).

I'm no longer using a Pi as a set-top box, but I loved how well this worked. Once of the things that impressed me (and I was lucky here) was that the Raspberry Pi Foundation thought to include an HDMI controller with the [**C**onsumer **E**lectronics **C**ontrol](https://www.onlogic.com/company/io-hub/what-is-consumer-electronics-control-cec/) protocol enabled.

CEC is part of the HDMI standard allows electronic devices to receive and send control signals and messages over the HDMI cable. Many Televisions and other devices have this built in, and our TV did, although LG calls it Simplink (it seems that every manufacturer calls it something different... That's helpful!). What this meant was that we could control Kodi using our TV remote control without any extra configuration.

### SpotifyD
I've used the Raspberry Pi computers for many things over the years from remote cameras to DHCP servers, but one of the things I'm using one of the older ones for right now is [SpotifyD](https://github.com/Spotifyd/spotifyd).

SpotifyD is (as the description says) "*An open source Spotify client running as a UNIX daemon.*". This means that I can set up an old Raspberry Pi running [Arch Linux](https://www.archlinux.org/) and run Spotify automatically without any GUI (graphical user interface), headless (i.e. no keyboard or monitor). I've hooked up the audio jack of the Pi to our livingroom stereo and now, using Spotify Connect I can send music from my laptop or tablet directly to our stereo with just a click. SpotifyD is always sitting there waiting for whatever music I want to hear.

## OpenMediaVault
I've experimented with a number of different NAS (Network Attached Storage) solutions over the years, including the BSD Unix-based FreeNAS, but I was so used to Linux, that BSD was difficult for me to get the hang of. It was also a bit frustrating that I couldn't easily install custom programs and tools in order for me to do new but not officially supported things.

Then FreeNAS developer Volker Theile decided to create the Debian Linux-based [OpenMediaVault](https://www.openmediavault.org/) and I was thrilled. I waited patiently for the first release (which took forever) and then set it up on our home server and never looked back.

One of the things that always bothered me about running a NAS server was the power requirements and the corresponding cost. Ever since the Raspberry Pi arrived I was trying to think of a way to use a single board computer like the Pi for this purpose. The Pi wasn't suitable because the USB 2.0 interface had slow transfer rates and the 100Mbit network connection was too slow. Besides, the controller for the USB and network was shared and they would be fighting for the same bandwidth.

### ODroid XU4
In the end I decided to purchase an ODroid XU4 as our Network Attached Storage server. The ODroid is a little single-board computer like the Pi, but with Gigabit networking and USB 3, which is much more suitable for connecting a USB drive to the network.

[![ODroid XU4](https://jiffyshop.com.au/SBC/380-home_default/odroid-xu4q.jpg "What a cute little thing!")](https://www.hardkernel.com/shop/odroid-xu4q-special-price/)

Our setup has Debian Linux with OpenMediaVault installed along with a number of custom pieces of software that aren't part of that NAS installation. OMV is very versatile and easy to use with its web-based interface and many plugins. I use it for sharing files between everyone in the family, for streaming movies, TV shows and music over the network and for downloading things. It can do a lot more that I'm not taking advantage of.

### PiHole
![PiHole Logo](https://pi-hole.net/wp-content/uploads/2018/12/pihole-text-logo-white.png)
One thing that OMV doesn't have a plugin for is the [PiHole](https://pi-hole.net/) software. Designed for the Raspberry Pi OS, this '*black hole for Internet advertisements*' is a way of filtering DNS requests from your network by using blacklists. The PiHole takes over DHCP (handing out network (IP) addresses) and DNS (resolving names to IP addresses) roles on the network and provides a nice web-based interface to allow you to control which addresses computers on your network are allowed to visit.

The main purpose that PiHole was designed for was to stop advertisements and Internet profilers and trackers. But there are blacklists available for all kinds of Internet resources such as pornography, violence and drugs. PiHole is very easy to set up once you have a Linux device on your network and, since I already had my ODroid running Debian, it was a cinch.

## Minecraft
![Minecraft Logo](https://www.minecraft.net/etc.clientlibs/minecraft/clientlibs/main/resources/img/header/logo.png)
The other network service that we've been running for a long time is a Minecraft server. Originally we had multiple Minecraft worlds running on a full-sized computer, but this bothered me because of the electricity requirements to run a computer that really wasn't being used all the time just in case someone wanted to use it.

When I bought the ODroid, I migrated our main non-modded Minecraft world, Irdya to it. I discovered [Paper](https://papermc.io), a version of the high-performance Spigot Minecraft server software and found a build compiled for the ODroid. That worked quite well, but I wanted a dedicated device for this.

When the Raspberry Pi 4 came out, with its Gigabit networking and USB 3 ports, I immediately knew that this was a better solution. We are now running Paper for Minecraft 1.16.2 and that's all the Pi is doing. I want to upgrade to a 64-bit version of the Raspberry Pi OS so I can take advantage of all of the available RAM for the Minecraft server's Java Virtual Machine.

Right now we have a Forge-based, modded server up-and-running called Magecraft which uses a custom modpack the guys have developed for them and their friends to play on. We use a whitelist and other measures to keep just anyone from connecting to the worlds.

## Roku
We wanted something simple for Nicole's mom to use with her TV in her basement apartment. We had satellite TV for awhile and we tried IPTV, but both were expensive and full of content we weren't interested in; endless channels but nothing to watch.

When we got rid of Netflix because we were sickened by their virtue-signalling corporate decision making we decided to try Amazon Prime since we could get free shipping as well as TV and movies. But we needed something like a set-top box. A Raspberry Pi is fine for our livingroom because we're all pretty tech-savvy, but I decided on a Roku Express for the basement because it's much simpler. Since it's in close proximity to the wireless router it connects and works just fine.