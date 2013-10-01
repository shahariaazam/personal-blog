---
title: Use XAMPP PHP CLI in your command line
layout: single_post
ogDescription: Use XAMPP PHP CLI in your command line instead of local PHP to execute PHP command in your command promt.
categories: [PHP]
tags: [tutorial, tips]
---

To use XAMPP's PHP as default PHP in your command line to execute PHP commands from
your command line/prompt you have to just follow the simple steps mentioned below&#58;

*in this tutorial I used UBUNTU as my OS*

Open your **terminal** and open **.bashrc** file by following command&#58;

{% highlight bash %}
sudo gedit ~/.bashrc
{% endhighlight %}

If you don't use GUI or **gedit** not installed then you can use **vim** instead of **gedit** like following

{% highlight bash %}
sudo vim ~/.bashrc
{% endhighlight %}

and just you have to add the following line at the end of your **.bashrc** file.

{% highlight bash %}
export PATH=/opt/lampp/bin:$PATH
{% endhighlight %}

Now restart your terminal and you are done!
Now type `php -v` to verify that it's working. this **php -v** command will show you the
*PHP version* used in your command line. Happy PHP'ing.