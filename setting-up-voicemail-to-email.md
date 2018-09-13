Title: Setting up voicemail to email
Date: 2014-04-04 20:11
Author: jamesleighton
Tags: geek, howto
Slug: setting-up-voicemail-to-email
Status: published

Ever been annoyed at how long it takes to retrieve your messages from Vodafone, Giffgaff, EE, or whoever runs your phone service? Me too. Press 1 to delete. Sorry, you need to listen to more than half to do that..... Yeah.... It's annoying. It's much easier to just receive an MP3 file in your inbox immediately after the message is left.

![Sample Voicemail Email](/images/aa-voicemail-email.png)

I found a cheap (£1.20/month) solution, which is actually pretty handy. You buy an incoming geographic UK landline from [Andrews and Arnold](http://aa.net.uk/telecoms.html) in whichever area code you'd like. Set it up so that it directs straight to voicemail (or busy, if you want to take calls on this new number too. It's up to you.) If you're reading this then feel free to leave me a message!

![AA Voip Settings](/images/aa-voicemail-settings.PNG)

Once this is working, set your phone to direct on busy/failed/no service to forward the call to your new number rather than their voicemail service. That's it!

![AA Voip Settings](/images/aa-voicemail-android.png)

This is possible with an iPhone. It's a little bit more annoying to set up, as Apple do not expose the more detailed call forwarding options within their interface. However, knowledge of the GSM commands means that you can set this up using the dialer. These codes can be found on [Wikipedia](https://en.wikipedia.org/wiki/Call_forwarding) with more detail of how they work. For a record, here are the (untested by me) activation codes that should work in Europe for iPhones.

#### If Busy

<div class="highlight">

    *67*[phone number]#

</div>

#### If Not Answered

<div class="highlight">

    *61*[phone number]#

</div>

#### If Out of Reach (No Service)

<div class="highlight">

    *62*[phone number]#

</div>
