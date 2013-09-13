---
title: strtotime() it is not safe to rely - error solution
layout: single_post
permalink: strtotime-it-is-not-safe-to-rely-error-solution
ogDescription: When you work with core PHP installation then sometimes your timezone was not configured. That is why you sometime see strtotime() it is not safe to rely error. Read this to solve this error.
categories: [PHP]
tags: [PHP, Tips]
---

Today in my new PC I was just using a PHP application and I saw a error that says the following error&#58;
{% highlight php %}
PHP Warning: strtotime(): It is not safe to rely on the system's timezone settings. You are required to use the date.timezone setting or the date_default_timezone_set() function
{% endhighlight %}

Then I just figured out that I installed the latest version of PHP manually and in my **php.ini** file I didn't tell PHP about my **default timezone**. Now I just open my **php.ini** file and uncomment the following line&#58;
{% highlight bash %}
[Date]
; Defines the default timezone used by the date functions
; http://php.net/date.timezone
date.timezone = Asia/Dhaka
{% endhighlight %}

I just uncomment the `date.timezone` line and assign value `Asia/Dhaka` as default timezone. To see all supported timezone in PHP, [click here](http://php.net/manual/en/timezones.php)

Now this **strtotime() it is not safe to rely error solution** types of error will be solved.