Title: Homepass with a Raspberry Pi 3
Date: 2016-06-23 00:00
Author: jamesleighton
Category: gaming
Tags: 3ds, raspberry pi
Slug: homepass-with-a-raspberry-pi-3
Status: published

I used to use [Homepass](http://homepass.info/) a few years back but my old Pi broke and I never got around to replacing it. I bought a pair of [Raspberry Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/)'s recently and decided to put one to use as a StreetPass relay for my and my girlfriend's 3DS as we seem to live in a desert of 3DS's right now. Shame!

The Raspberry Pi 3 is perfect for this purpose as you need nothing more than an ethernet cable to your router and power. No need for a USB wireless adapter making everything that much simpler.

If you're wondering what Homepass or Streetpass is, then no fear...

> HomePass is a homebrew method of fooling your 3DS system into believing a Global StreetPass Relay exists in your house.
>
> Nintendo released an update to the 3DS StreetPass system in the beginning of August 2013, that would allow users to receive and transmit StreetPass data via Nintendo Zone Wifi Access Points.
>
> Nintendo calls this new system “StreetPass Relay”. Over at GBATemp.net, great minds came together and figured out how to utilize your home WiFi Router/Access Point as a Nintendo Zone StreetPass Relay — but not just a local one, a GLOBAL relay. You will be able to StreetPass people from around the world. Want tons of streetpasses in a single day, without ever leaving the house? Read on :)

 

I found some instructions and an image on Reddit which you can find [here](https://www.reddit.com/r/3DS/comments/4h8exo/so_ive_managed_to_get_a_raspberry_pi_3_working_as/). This preprepared image deals with the bridging, firewall rules, run schedule etc.

If you are using Windows, try using Win32diskimager to write the Pi image to your SD card. On a Mac, I used Apple Pi Baker to great success. I tried a couple of times using terminal but it wouldn't boot successfully. Apple Pi Baker solved my issue.

I have mine set as default to attempt to run every 6 minutes, with a 2% chance of succeeding. The default is 20%. Every six minutes, the script will attempt to start the access point with a Relay MAC address.

It is effectively a roll of the dice, as you don't need to be getting StreetPass hits every 6 minutes all day. Well, maybe you do. Then you can set the run chance to 100%. My relay should effectively run 6*24*.02 times per day on average (about 3) which suits my needs perfectly.

Happy Streetpassing!
