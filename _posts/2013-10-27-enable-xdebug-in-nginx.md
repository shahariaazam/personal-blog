---
title: How to enable xDebug in Nginx
layout: single_post
ogDescription: Learn how to enable xDebug powerful PHP debugger in your nginx powered server. It will also work on Apache2 as well
categories: [Ubuntu, PHP]
tags: [php, xdebug]
---

To enable **xDebug** in your **nginx** server you just first install xdebug by **pecl** command.

{% highlight bash %}
sudo pecl install xdebug
{% endhighlight %}

Now _xdebug_ is installed in your system. Now find exactly where **xdebug.so** file was downloaded.

You have to find it in **/usr/lib/php5/(somewhere in this directory)**

Now after find the xdebug.so you have to open your **php.ini** file and add the following command.

{% highlight bash %}
zend_extension=locationOfYourxDebugfile
xdebug.remote_port=9000
xdebug.remote_enable=On
xdebug.remote_connect_back=On
xdebug.remote_log=/var/log/xdebug.log
{% endhighlight %}

Now restart your nginx and **php5-fpm** to load this xdebug. In this same way you can install xdebug for your Apache2.

For apache, setup like the above and after configuring just restart your apache. And you are done!