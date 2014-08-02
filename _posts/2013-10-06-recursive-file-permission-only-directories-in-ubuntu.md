---
title: Recursive file permission to only Directories/Files in Ubuntu
layout: single_post
ogDescription: Learn how to set permission on only directories or files recursively in Ubuntu
categories: [Tips, Ubuntu]
---

Suppose, you think that you just copied a large directory or application or files to any other place inside your operating system.
Then you need to change the file permission to all the files or to all the directories
recursively in your Ubuntu operating system.

In this case, don't worry I will show you how to set recursive directories only or files only permission
from your terminal in Ubuntu.

Simply open your **terminal** and write down the following command to set permission
to only **directories** recursively.

{% highlight bash %}
find /opt/lampp/htdocs -type d -exec chmod 755 {} \;
{% endhighlight %}

_In the above command all **directories** under **/opt/lampp/htdocs** will be assigned with 755 (-rwxr-xr-x) permission sets recusively._

{% highlight bash %}
find /opt/lampp/htdocs -type f -exec chmod 644 {} \;
{% endhighlight %}

_In the above command all **files** under **/opt/lampp/htdocs** will be assigned with 644 (-rw-r--r--) permission sets recusively._
