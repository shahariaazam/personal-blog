---
title: Install Redis Cache engine in Ubuntu
layout: single_post
ogDescription: learn how to enable Redis cache engine in your Ubuntu server. It is pretty necessary for PHP programmer to use Redis as their cache engine.
categories: [Ubuntu, Tips]
---

Sometimes programmers think a lot much about to optimize their application performance. In this sense, we got the idea of **Caching**. Now the fact is which Cache engine is best, fast and suitable. I will not go through that debate. Today I am writing you about how to install Redis Cache server/engine in your Ubuntu OS. Let's start from the beginning. 

First you have to install `redis-server` in your ubuntu by running the following command.

{% highlight bash %}
sudo apt-get install redis-server
{% endhighlight %}

After that we have to install [PHPRedis](https://github.com/nicolasff/phpredis) from the scratch.

Now run the following command sets. 

{% highlight bash %}
sudo git clone https://github.com/nicolasff/phpredis.git
phpize
./configure [--enable-redis-igbinary]
make && make install
{% endhighlight %}

_if you have not GIT installed on your computer then you have to install git with `sudo apt-get install git` command._

After compiling and install phpredis just copy the **redis.so** file to your PHP extension library directory by running the following command.

{% highlight bash %}
sudo cp modules/redis.so yourPHPExtensionLibrary/redis.so
{% endhighlight %}

_you can find your PHP extension library directory from phpinfo()_

Now it's time to load this `redis.so` module in your PHP **INI** file. Just write down `extension redis.so` at the bottom of your **php.ini** file and restart your webserver.

Your redis engine is ready. To get the further installation system and details please [read this PHPRedis GitHub Repo](https://github.com/nicolasff/phpredis).
