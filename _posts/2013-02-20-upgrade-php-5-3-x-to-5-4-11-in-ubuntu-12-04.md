---
title: Upgrade PHP 5.3.x to 5.4.11 in UBUNTU 12.04
layout: single_post
permalink: upgrade-php-5-3-x-to-5-4-11-in-ubuntu-12-04
categories: [PHP, Ubuntu]
tags: [PHP5, Tips, Tricks, Tutorial]
---
Recently I was just curious about what's coming with PHP's latest release. I am using 5.3.10 in my UBUNTU PC since long time. Now I need to update my PHP 5.3.10 to 5.4.11 (according to php.net it is the latest stable release of PHP). I am using UBUNTU 12.04 LTS. So I am now writing this post what was tested on this OS. I was just installed Apache2 and PHP5 on my PC. Now I am just writing about how to upgrade my PHP. It's pretty simple task I used.

#####Step 1
-	First run the following program to `update` and `upgrade` all of your stuffs in your linux operating system.

{% highlight bash %}
sudo apt-get update
{% endhighlight %}
*It will update your software list* and then type the following command to upgrade your system.
{% highlight bash %}
sudo apt-get upgrade
{% endhighlight %}

Now all of your stuffs are upgraded. Now add package repository by typing the following command.

#####Step 2

{% highlight bash %}
sudo add-apt-repository ppa:ondrej/php5
{% endhighlight %}

But remember, it will not upgrade your PHP to it's latest release. I don't know why but I saw a error like **The following package will be as like it was..**.

#####Step 3
It's the final step. Now you need to run this command to finally upgrade your PFP distribution.

{% highlight bash %}
sudo apt-get dist-upgrade
{% endhighlight %}

And now your PHP will start upgrading to it's latest stable release. Happy PHP-ing.