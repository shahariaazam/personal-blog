---
title: Enable OpCache in PHP5 to boost your application
layout: single_post
ogDescription: To boost your PHP driven web application, in PHP5.5 you can easily enable Zend OpCache which will increase your application performace.
categories: [PHP]
---

After lots of folk PHP5 has released [Zend OpCache] engine with core PHP5.5 and PHP internals will continue to develop PHP with this Zend OpCache in future releases of PHP.
It's great news for all the PHP lovers who used APC cache to boost their application performance. But keep in mind, APC is no more supported with PHP5.5 and may not be for future release also.
So here you should love **OpCache** (_original name: Zend OpCache_) for tweaking your application performance.
Although this opCache is built-in in PHP5.5 so you just have to enable this from your **php.ini** file and you are ready to go.
So let's see how you can enable this OpCache in your environment. 

Just open your PHP `php.ini` file (location may depends on your environment) and search for opcache and here you will see the configuration like below.

{% highlight ini %}
[opcache]
; Determines if Zend OPCache is enabled
;opcache.enable=0

; Determines if Zend OPCache is enabled for the CLI version of PHP
;opcache.enable_cli=0

; The OPcache shared memory storage size.
;opcache.memory_consumption=128

; The amount of memory for interned strings in Mbytes.
;opcache.interned_strings_buffer=4
{% endhighlight %}

Now you just have to remove `;` from `;opcache.enable=0` and replace **0** with **1**. Also do the same for `;opcache.enable_cli=0`.

And if you want to modify share memory storage size then just uncomment it and change the integar value. So after change it should look like

{% highlight ini %}
[opcache]
; Determines if Zend OPCache is enabled
opcache.enable=1

; Determines if Zend OPCache is enabled for the CLI version of PHP
opcache.enable_cli=1

; The OPcache shared memory storage size.
opcache.memory_consumption=256

; The amount of memory for interned strings in Mbytes.
opcache.interned_strings_buffer=4
{% endhighlight %}

Now you have to restart your apache or if you are using nginx then you have to restart `php5-fpm`. Enjoy!

**Tools to monitor your server's OpCache status**
Founder of PHP [Rasmus Lerdorf](https://github.com/rlerdorf) developed few snippet to test the OpCache status for your environment.
You can download that from [here](https://github.com/shahariaazam/opcache-status). Download this repo and put it anywhere in your server and browse **opcache.php** and it will display the current status of your OpCache engine like the following image.
![Zend OpCache Status Screenshot](http://i.imgur.com/Z7Zp61w.png)
