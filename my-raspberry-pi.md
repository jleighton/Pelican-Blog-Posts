Title: My Raspberry Pi
Date: 2012-06-28 11:03
Author: jamesleighton
Category: gadgets
Tags: raspi
Slug: my-raspberry-pi
Status: published

I recently received my Raspberry Pi a few weeks back, and have been wondering what I should do with it! Today, I worked it out.... It's primary use is going to be forwarding emails from my Scan-to-email printer onto Gmail (since it doesn't support SSL, therefore doesn't play nicely with Gmail) and the secondary use it going to be for making time lapse videos of my mum's seedlings. We already have the network camera set up, but no-one bothers to look at it because the interface is terrible.

The first objective seems to require something like Postfix or Sendmail, but I am trying to find something a bit more lightweight. It literally just needs to connect to gmail and forward the emails on. Seems pretty simple, hopefully it will be!

Part 2 seems alright too. I'll get a reasonably large USB memory stick sorted so that images coming into the Pi (probably via FTP) don't fill the SD and then use some shell scripting and [this method](http://www.cenolan.com/2009/05/simple-time-lapse-video-in-linux/) to automatically convert each days of images into video files which can be plonked straight onto dropbox and then uploaded to Youtube

As for a case, I just bought one of eBay for around £18… It’s arrived now I’m retyping this up, so here is a handy picture. As you can see, it doesn’t cover the sides but I think it gives adequate protection for the Pi. This also means that heat dissipation shouldn’t be an issue! Putting it together was pretty nifty, too.

![My new bike](/images/raspi.jpg)

Now that I’ve finished uni I’m definitely going to dive head first into making my Pi a useful bit of kit. Expect some updates over the coming weeks!
