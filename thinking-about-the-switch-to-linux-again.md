Title: Thinking about the switch to Linux... (Again)
Date: 2013-03-03 11:25
Author: jamesleighton
Category: linux
Tags: geek
Slug: thinking-about-the-switch-to-linux-again
Status: published

I've used various operating systems over the last ten years... Windows XP, Vista, 7 and 8. Apple's OS X. Linux distributions like Ubuntu (I found some old 4.10 install discs a few months back), Debian, and more recently [Crunchbang](http://crunchbang.org/). My primary operating system currently is Windows 8 (although I was perfectly happy with 7 I just like shiny toys.)

Windows 8 gets a bad rap. Personally I think it's undeserved as everything new and different is disliked initially. Sure losing the start menu is pretty damn drastic, but you don't even need to ever see the start 'screen' ever if you don't want to. Press Win+D and you're back at your old desktop. Install a start menu replacement and be happy about all the new stuff in Windows 8 that actually matters. The [inbuilt virtualisation](http://technet.microsoft.com/en-us/library/hh857623.aspx) stuff is cool, likewise the faster boot ups and (subjectively) snappier interface.

What currently ties me to Windows is Microsoft Office. It's tied me for a long time. Last year for my final year HND project I got to watch one of the guys struggle with OpenOffice (now LibreOffice) trying to complete his 5000 word report. All sorts of things were just more difficult than they needed to be. Personally being used to Office is a really strong tie. If there was a way to run 100% native 100% compatible Microsoft Office I'd be running Linux as my primary OS in a flash. Maybe I'd still need to reboot for games that don't run but that's secondary and not as much of a concern. Rebooting to use office is a pain; rebooting for games... well if the majority of my games are separated that might do wonders for my productivity.

==Getting things to work in Linux==

Saying that I removed Ubuntu from my PC this week, fiddled around with Grub (nearly managed to hose my Windows install thankfully I got it booting again), and reinstalled the last version of Crunchbang in it's place. The experience was a good one.

Whilst some of this isn't specific to Crunchbang, I still think it's good to let people know that Linux is becoming much more viable as a computing platform for the majority as time goes on. I booted up; my graphics drivers work (as in my native resolution 1920x1200 is functional) out of the box. My ethernet card is detected and although that needed [manual config](/2013/03/using-linux-computer-in-university-halls.html) so does Windows or Mac due to my uni using 802.1x authentication.

Once I had my network working, Crunchbang offered to update everything for me and install various packages such as java, Libre Office, and a few others that I can't remember. There was a bit of a fuss when installing the latest AMD graphics drivers which is made easier using a script called SMXI. It worked brilliantly until I had to reboot to unload the old un-needed kernel modules. From here, you're supposed to run 'sgfxi' at a root prompt to allow the installation of the drivers to continue.

This is great except wpa\_supplicant or something else important in my network configuration hadn't been loaded. The trick is to call 'sgfxi -W' which skips the internet check as everything should of already been downloaded anyway. Worked great from there on and now I had the latest graphics drivers ready to go. If you get stuck after the reboot because your internet connection hasn't connected give the above command a shot!

On the next boot I had a play with my external USB drives and was really surprised and pleased to see that whilst they are formatted as NTFS I could read them just fine. Playback in VLC worked as expected but this is the sort of thing that has changed so much since my earliest forays into Linux nearly ten years ago. Nothing worked back then. It was fun, though! Youtube worked fine, my sound card was working fine. Pretty much everything was working with minimal tinkering and configuration.

I still haven't managed to get my printer to work (Samsung ML-2160) but that's more likely to be a matter of persistence rather than it not actually working at all. The right driver is just waiting to be found! My next task is to replicate the ethernet sharing that I currently use with Connectify in Windows. I've read that dnsmasq should be able to do what I want (Bridge eth0 to eth0; provide DHCP on eth0 which is plugged into a minuture wifi access point providing wifi access to my consoles, tablet, kindle etc.)

Other than that, reinstalling Crunchbang for the first time in about three years was really good. I even got the NMR software that we use in chemistry to run (albeit I had to fiddle with the package as it was i386 rather than amd64, but I got that running in the end. Just need to send off for my licence if I decide to go full time Linux)

I am looking for a nice alternative to ChemBioDraw but I see that ACD/Labs have an older version of [Chemsketch](http://www.acdlabs.com/resources/freeware/) available for free that works with Wine so I'll need to look into that. As long as it draws molecules it'll do. Don't need anything much more fancy than that. I also noticed that with all the Humble Bundles that I've been buying I have a load of native linux games to test. Yet another thing to take up my time! Of course, OpenTTD runs brilliant on Linux ;)

Linux is definitely looking more and more viable as a platform for me personally. If you don't have the hangups of hanging on to Microsoft Office like I do; and you need no other platform specific programs then take a look at it. You might be surprised at how well it runs!
