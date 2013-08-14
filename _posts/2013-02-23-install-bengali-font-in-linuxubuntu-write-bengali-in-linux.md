---
title: 'Install Bengali font in Linux/Ubuntu &#8211; Write Bengali in Linux'
author: admin
layout: single_post
permalink: install-bengali-font-in-linuxubuntu-write-bengali-in-linux

categories: [Tips and Tutorial, Ubuntu]

tags: [bengali, how-to, linux, ubuntu, tutorial]
---

Ubuntu hasn’t any default solution for *Bengali font* or *Bangla input methods*. To use *Bangla* in your Linux PC you have to install it manually first. It’s pretty simple. Just follow my following steps.

{% highlight bash %}
sudo apt-get install ibus ibus-m17n m17n-db
{% endhighlight %}

The above command will install **iBus (input methods)**, `ibus-m17n` and `m17n-db` in your system.

Now you have to write the following command to setup iBus.

{% highlight bash %}
sudo ibus-setup
{% endhighlight %}

now you will see a ibus setup window to configure. (see following image)

![Setup iBus in Ubuntu](/assets/img/public/Bangla-setup-in-UBUNTU.jpg)

Select `Unijoy (m17n)` as Input methods from the drop down list. Select it and click on **Add** from the right side. In this same way also add `ispell (m17n)` for **English** support also. select it and add it. Now after adding both `Unijoy` and `ispell` just close the setup dialogue. And you are done!!

