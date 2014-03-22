---
title: Transfer server files to another server by rSync
layout: single_post
ogDescription: Read about how to transfer files from a server to another server easily with rsync. It's super easy if you can read it.
categories: [linux]
---

To copy files from a server to another server is not a complex task anymore. This blog post will give you a solid and a very easy steps to accomplish this hard task so much easily. To transfer your files from source server to destination server you must have to enable **ssh** in both server. If you haven't, then you can [read it](https://help.ubuntu.com/community/SSH/OpenSSH/Configuring) to enable ssh for your server.

We will do all this copy/paste things with [rsync](http://www.samba.org/rsync/). rSync is really a super useful stuff in this types of case. To write this post I used Ubuntu 13.04 server as my OS. So I think it will work on most **unix** OS.

So just you have to install rsynch on your source server and desination server by typing the following command:

{% highlight bash %}
sudo apt-get install rsync
{% endhighlight %}

it will be automatically installed on your server. Now you have to run the following command in your destination server to copy all the files from source server via ssh protocol. It works fast and really interesting.

Run the command in your destination server:
{% highlight bash %}
rsync -avzhe ssh username@yourRemoteServerIPorDomain:/DirectoriesNeedToBeCopied/ /LocationWhereFilesWillBeCopied
{% endhighlight %}

after running the following command from your destination server. It will do all the things. Rsync will connect to your source server and it will promopt you to give the password to logon to source server after that it will start copying files, directories and everything from the source server and save to your destination server. To know more details about rsync command argument you can go to [rSync MAN page](http://rsync.samba.org/ftp/rsync/rsync.html).

And if you want to upload the transferred files to your dropbox as a backup system you can do that after synchronizing with rsync. You can read about [Upload server files to Dropbox](http://blog.shahariaazam.com/backup-your-linux-cloud-server-to-dropbox-easily).
