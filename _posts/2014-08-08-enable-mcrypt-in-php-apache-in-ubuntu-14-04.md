---
title: Enable mCrypt extension in your PHP5 in nGinx server in Ubuntu
layout: single_post
ogDescription: Learn how to enable mCrypt in your LEMP stack in Ubuntu
categories: [PHP, Ubuntu]
---

[mCrypt](http://php.net/manual/en/intro.mcrypt.php) is one of the best and most popular Cryptography Extensions in PHP5. To install it with your PHP5 in your NGinx server for Ubuntu 14.04 please install it with following command

{% highlight bash %}
sudo apt-get install php5-mcrypt
{% endhighlight %}

and then restart your NGinx server with `sudo service nginx restart`. But sometimes it may fails to load your mCrypt extension with your PHP5. If you face those types of problem just execute the following command in your Ubuntu 14.04 command line and restart Nginx.

{% highlight bash %}
sudo phpenmod mcrypt
{% endhighlight %}

Now you have mcrypt enabled in your PHP5. Keep coding!
