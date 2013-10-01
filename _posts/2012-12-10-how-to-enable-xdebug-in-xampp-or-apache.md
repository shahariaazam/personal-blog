---
title: How to enable xDebug in XAMPP or Apache
layout: single_post
permalink: how-to-enable-xdebug-in-xampp-or-apache
ogDescription: Learn how to enable xdebug in xampp or apache in Windows. Pretty easy tutorial that can help you to debug php application smartly.
categories: [PHP, xDebug]
tags: [xdebug, php, debug, xampp, apache]
---

######xDebug for PHP Coders
**xDebug** is a very popular and famous debugging utility for PHP programmers. It actually works with Apache. So to activate or **install xDebug** for **PHP** coders you just follow the steps given below..

#####Step 1:
Just open your php.ini file and find out with &#8216;xdebug&#8217; then you can see like
{% highlight bash %}
;zend_extension = "C:xamppphpextphp_xdebug.dll"
{% endhighlight %}
Then just remove &#8216; ; &#8216; from that above line and just copy the following lines of code in your php.ini file.

{% highlight bash %}
xdebug.remote_enable=On
xdebug.remote_host="localhost"
xdebug.remote_port=9000
xdebug.remote_handler=dbgp</pre>
{% endhighlight %}
Now just restart your Apache and from now you can debug your server output result more smartly. Happy coding!!