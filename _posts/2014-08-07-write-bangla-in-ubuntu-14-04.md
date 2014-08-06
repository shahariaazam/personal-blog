---
title: How to write bangla in Ubuntu 14.04
layout: single_post
ogDescription: Learn how to write Bangla in Ubuntu 14.04
categories: [Linux, Ubuntu]
---

Let me say at first to the reader of this post that I am not talking about Phonetic bengali writing. I am talking about write with original **Unijoy** keyboard layout.

Last year I wrote another blog post on [Install Bengali font in Linux/Ubuntu – Write Bengali in Linux](http://blog.shahariaazam.com/install-bengali-font-in-linuxubuntu-write-bengali-in-linux). But that was for older Ubuntu version. Right now the latest Long Term Support (LTS) release of Ubuntu is 14.04. So to **write bengali in Ubuntu 14.04** we have to change or doing something little bit different.

Here is the process. From your Ubuntu command line just install the following packages by running the commands below-

{% highlight bash %}
sudo apt-get install ibus-m17n m17n-db m17n-contrib ibus-gtk
{% endhighlight %}

And to run the **iBus Daemon** to select the bengali keyboard layout you have to run the following command from your Ubuntu 14.04 command line-

{% highlight bash %}
sudo ibus-daemon -xdr
{% endhighlight %}

![screenshot](http://i.imgur.com/og9lP0J.png)

Now you will have to click on the **+** icon to add **Bengali Unibijoy keyboard** layout from the list. See the screenshot below-

![screenshot](http://www.webpagescreenshot.info/i3/53e288bf6cf160-08628765)

Select Bengali (unijoy m17n). That's it. Now according to your keyboard shortcut you can change keyboard layout (Bengali/English) as when you want. Happy bengali writing!

After doing the configuration from **Text entry settings** 
