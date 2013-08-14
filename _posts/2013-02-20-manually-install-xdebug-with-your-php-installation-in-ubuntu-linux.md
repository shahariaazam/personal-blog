---
title: Manually install xDebug with your PHP installation in UBUNTU/LINUX
layout: single_post
permalink: manually-install-xdebug-with-your-php-installation-in-ubuntu-linux
ogDescription: Try it out the easier system if you are lucky and using windows. Now let&#8217;s assume that you haven&#8217;t installed xDebug yet! Now we have to install xDebug. Now to do that first we have to install PHP PEAR. To install PEAR let&#8217;s type the following command. [crayon-520b7b66ef8ce962637155/] Now if it says that you have [&hellip;]
categories: [PHP, xDebug, Ubuntu]
---

Now let’s assume that you haven’t installed xDebug yet! Now we have to install xDebug. Now to do that first we have to install PHP PEAR. To install PEAR let’s type the following command.

{% highlight bash %}
sudo apt-get install php5-dev php-pear
{% endhighlight %}

Now if it says that you have already the latest PHP Pear. Then ready to move forward. Now to install xDebug you have to write down the following command.

{% highlight bash %}
sudo pecl install xdebug
{% endhighlight %}

After successfully installing `xDebug`. You have to add the following code in your **php.ini** file.

{% highlight ini %}
[xdebug]
; xDebug Configuration
extension=xdebug.so
{% endhighlight %}

After writing save php.ini and restart Apache. Yahooooooooo!!!!!!! Now you are getting colorful debug information of your program in PHP.

If you are using PHP installed by `XAMPP` on your Linux PC then just write the following command for installing `xdebug`.

{% highlight bash %}
sudo /opt/lampp/bin/pecl update-channels
sudo /opt/lampp/bin/pecl install xdebug
{% endhighlight %}

It’s for just installing **xdebug** on your `/opt/lampp` directory

Now you are done!! You can try to check it by using var_dump inside your code. happy coding!!