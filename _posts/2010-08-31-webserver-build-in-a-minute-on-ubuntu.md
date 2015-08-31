---
title: Web Server build in a minute on Ubuntu Machine
layout: single_post
ogDescription: Prepare your Ubuntu machine for Web Server. LEMP stack with one click installer. Save your time. Up and run your nginx web server in a click.
categories: [Linux, Ubuntu]
---

I guess, you want to make your Ubuntu server UP & running within few minutes with one click that will install all the essential packages for your web server. I created the following script that you can run right after installing your Ubuntu OS in your machine.

I tested this script over Ubuntu 14.04 LTS and nGinx as web server.

I created the following shell script for (a) Installing Common packages, (b) Configuring Virtual Host

You just need to run the installer. In your terminal just write down the following command and it will start installing all the essential thing and after that browse localhost or with server IP address and you are supposed to see the default nginx server page.

{% highlight bash %}
sudo wget https://gist.githubusercontent.com/shahariaazam/b63b72da0afbff195492/raw/db0ff5f553fdb25cf3bd9da64ec942cf09b31ab7/make_ubuntu_ready.sh
sudo chmod a+x make_ubuntu_ready.sh
sudo ./make_ubuntu_ready.sh
{% endhighlight %}
And browse ['http://localhost'](http://localhost)
<script src="https://gist.github.com/shahariaazam/f8884d4ed811eeb08b87.js"></script>
