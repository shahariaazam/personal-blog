---
title: Install Windows 7 from any USB device
layout: single_post
permalink: install-windows-7-from-any-usb-device
categories: [Windows 7]
tags: [Tips, Tricks, Tutorial, Windows 7, Installation]
---

This is a very common question for all computer users and it's even more necessary to know about to install windows on Netbook who hasn't any CD-ROM attached with Computer. So here is the tutorial you should read it completely to install windows 7 from any kinds of USB device.

#####Step 1

Plug-in your USB drive with your PC. And backup all contents from USB device and format it. Now go to **Start menu** > **All programs** > **Accessories** and right click on **Command Prompt** and click on run as administrator.

#####Step 2

Write the following command.

{% highlight bash %}
DISKPART
LIST DISK
{% endhighlight %}

See your USB Drive's Drive number. In my PC it is DRIVE 1. Check for yours.Â Here I think that your disk drive no is *Disc 1*. Use this according to your drivers information.

Now serially write the following command. After each command press 'Enter' key. and then type next.

{% highlight bash %}

SELECT DISK 1

CLEAN

CREATE PARTITION PRIMARY

SELECT PARTITION 1

ACTIVE

FORMAT FS=NTFS

ASSIGN

EXIT
{% endhighlight %}

Now please open your windows 7 installation media. I assumed that it is in your **F** drives **Windows 7** folder. In your case, it can be different. Now write the following command.

{% highlight bash %}
CD boot
{% endhighlight %}
**navigate to windows 7 installation directory's boot folder**

{% highlight bash %}
BOOTSECT.EXE /NT60 H:
{% endhighlight %}

 (here 'H' is your USB driver's driver path/name)

after executing that command you will see like **Bootcode was successfully updated all target volumes.**

#####Step 3

Now copy your windows 7 installation files into your USB device (in my case it was H). It is different for you.

#####FINAL STEP

Restart your computer (which needs to be install windows). And now set boot device is **USB drive**. and restart computer. Now you will see that PC is being boot from your USB drive. Now you can easily install windows. Thank you.

 