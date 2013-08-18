---
title: Re-configure your LOCALE settings on Ubuntu
layout: single_post
ogDescription: Re-configure your locale settings on Ubuntu to avoid lots of ugly errors. Very easy steps to follow on.
categories: [Ubuntu]
tags: [Ubuntu]
---
Sometimes I saw an error to do a task in my Ubuntu PC. The error was something like `invalid byte sequence in us-ascii`.

Then after searching a lots of solution over net I found out that `local settings` of my Ubuntu was messed up. And it's really important to make your locale settings correct to avoid lots of ugly error.

To check your existing locale configuration of Ubuntu, please type the following command&#58;

{% highlight bash %}
sudo locale
{% endhighlight %}

If there is something wrong or it's not `en_US.UTF-8` then you should re-configure your **locale settings** with `en_US.UTF-8`. To do that open terminal and write down the following command&#58;
{% highlight bash %}
sudo locale-gen en_US.UTF-8
{% endhighlight %}

Then it will automatically configure your locale. Restart your terminal or PC and have fun!!