Title: SSH Login Notifications using Pushbullet
Date: 2014-11-08 17:00
Author: jamesleighton
Category: linux
Tags: geek
Slug: ssh-login-notifications-using-pushbullet
Status: published

Pushbullet is a great app that allows you to share notifications to and from your phone/computer. I recently saw [Dead Man's Snitch](https://deadmanssnitch.com/ "Dead Man's Snitch") (a service which alerts you about cron jobs) and figured I could probably replicate the most important functionality for me using Pushbullet. After all, being a poor student is all about saving as much money as possible!

Playing around with the [Pushbullet API](https://docs.pushbullet.com/ "Pushbullet API Documentation") whilst setting up backup notifications for my servers, I wondered if I could get a push notification every time (hopefully) just me logged in via SSH.

I ended up with the following bash script that can be added to your bash login script (\~/.bash\_profile)

+--------------------------------------+--------------------------------------+
| <div class="linenodiv">              | <div class="highlight">              |
|                                      |                                      |
|     1                                |     #!/bin/bash                      |
|     2                                |     IP=($SSH_CLIENT)                 |
|     3                                |     name=$(whoami)                   |
|     4                                |     string="SSH Login from $IP for $ |
|     5                                | name"                                |
|                                      |     /home/admin/pushbullet/pushbulle |
| </div>                               | t push all note "$string"            |
|                                      |                                      |
|                                      | </div>                               |
+--------------------------------------+--------------------------------------+

It uses this library from [Github](https://github.com/Red5d/pushbullet-bash), but could do it without the library at all if you're not as lazy as I am. More Pushbullet goodness soon!

![pushbullet](https://jamesleighton.files.wordpress.com/2016/11/pushbullet.png){.alignnone .size-full .wp-image-544 width="540" height="350"}
