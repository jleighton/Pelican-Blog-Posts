Title: Using a Linux computer in University halls
Date: 2013-03-08 11:25
Author: jamesleighton
Category: linux
Tags: geek, howto, uni
Slug: using-a-linux-computer-in-university-halls
Status: published

If you run Linux on a PC or laptop in halls of residence you may of realised that most universities are using 802.1x authentication on their networks. It's great, secure all that. It can just be a pain to set up. I'm currently in halls at Bangor University and couldn't figure out how to get it all working in Ubuntu or Crunchbang. To be fair, it's pretty unreliable in Windows too... "Unable to authenticate!"... Grr but I digress.

I found this [guide](http://www.inf.aber.ac.uk/advisory/faq/511) on Aberystwyth University's website, and it worked great. Basically you need to download and make sure that wpa\_supplicant is installed (It should be in pretty much all modern Linux distros), then create a config file for it using the details on the page linked. I'll paste them below in case they ever take the page down.

Start up a command line interface and create a directory by typing:

<div class="highlight">

    mkdir /var/run/wpa_supplicant

</div>

Using a text editor create a wpa\_supplicant.conf file in /etc/wpa\_supplicant. Inside this file enter the following lines:  
\# BEGIN wired network configuration

<div class="highlight">

    ap_scan=0

    ctrl_interface=/var/run/wpa_supplicant

    network={ 
          key_mgmt=IEEE8021X 
          eap=PEAP 
          phase1="peaplabel=1" 
          phase2="auth=MSCHAPV2" 
          identity="your University email address" 
          password="your University password" 
    }

    # ENG wired network configuration

    Open a command terminal window and type:
    sudo chmod 600 /etc/wpa_supplicant/wpa_supplicant.conf

    Edit /etc/network/interfaces with the following. (The bits in bold)
    #BEGIN

    auto lo
    iface lo inet loopback

    auto eth0
    iface eth0 inet dhcp
    wpa-driver wired
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf

    #END

</div>

Restart your network card by typing  
sudo /etc/init.d/networking restart

You should now be connected to the University network

You'll have to do a bit of experimenting with the identity field. Aber wants your entire uni email whereas at Bangor I just needed my username for it to work. Try both until it works. I'm fairly certain these settings are going to be fairly universal for all uni's who utilise 802.1x authentication systems.
