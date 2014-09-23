---
title: Enable FTP Passive mode in PureFTP
layout: single_post
ogDescription: Enable FTP passive mode in your PureFTP in linux server
categories: [Cloud Computing, Linux]
tags: [Cloud Server]
---
To connect with your FTP server it is recommended to use Passive mode for all connection. And to do that you have to enable passive mode on your PureFTP package in your server.

Simply go to your PureFTP config file and remove enable **passivePortRange** option in config file. Open the config file with your suitable editor

{% highlight bash %}
sudo vi /etc/pure-ftpd.conf
{% endhighlight %}

Remove the comment (#) from the beginning of the line which contains the PassivePortRange option.

Change that line to the following:
`PassivePortRange 49152 65534`

Save the changes to the configuration file.

Now restart pureFtp and you can connect to your FTP server with Passive mode.
