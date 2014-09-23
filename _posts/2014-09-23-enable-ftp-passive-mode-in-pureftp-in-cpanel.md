---
title: Enable FTP Passive mode in PureFTP in your cPanel server
layout: single_post
ogDescription: Enable FTP passive mode in your PureFTP in your centOS powered cPanel server
categories: [Cloud Computing, Linux]
tags: [Cloud Server]
---

To enable the passive port range for Pure-FTPd, perform the following via the command line as the root user:

- Open the /etc/pure-ftpd.conf configuration file in your preferred text editor.
- Remove the comment (#) from the beginning of the line which contains the PassivePortRange option.
- Change that line to the following: 
  `PassivePortRange 49152 65534`

- Save the changes to the configuration file.
- Run the sudo /usr/local/cpanel/scripts/restartsrv_ftpserver command to restart the server.

_These configuration changes may be overwritten by system updates. To make these changes permanent, perform the following additional steps via the command line as the root user:_

- Run the `sudo rm -f /var/cpanel/conf/pureftpd/main.cache` command to clear the cache.

- Run the `sudo echo "PassivePortRange: 49152 65534" >> /var/cpanel/conf/pureftpd/main` command to append the passive ports to the configuration file.

Now if the port number is not opened in your iptables then do the following to enable this passive mode port range enable in your iptables.

{% highlight bash %}
sudo iptables -I INPUT -p tcp --dport 49152:65534 -j ACCEPT
sudo service iptables save
{% endhighlight %}

[This articles](http://blog.shahariaazam.com/enable-ftp-passive-mode-in-pureftp) also recommended for you to read.
