---
title: Backup your linux cloud server to dropbox easily
layout: single_post
ogDescription: Take backup of your cloud linux server and save your backup to dropbox easily by following few simple steps.
categories: [linux]
---

Today I will write about a very important topics which you need in your critical time. It's all about **taking backup of your cloud linux server and save the backup to your dropbox**. You can do it easily after reading this post. Please do all the things according to my post and get free from your tension.

**Tools You should use:** [Dropbox](http://www.dropbox.com)

**Operating system I have covered for this tutorial:** Ubuntu 13.04 Server

**Step 01**
- Install dropbox in your server by following the steps mentioned below:

**[Install Dropbox via command line](https://www.dropbox.com/install?os=linux)**
The Dropbox daemon works fine on all 32-bit and 64-bit Linux servers. To install, run the following command in your Linux terminal.

32-bit:

{% highlight bash %}
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86" | tar xzf -
{% endhighlight %}

64-bit:

{% highlight bash %}
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -
{% endhighlight %}

Next, run the Dropbox daemon from the newly created .dropbox-dist folder.

{% highlight bash %}
sudo ~/.dropbox-dist/dropboxd
{% endhighlight %}

**Step 02**
- Now just compress all of your targeted directories or even you can compress full of your system by following tar command.

{% highlight bash %}
sudo tar cf yourDestinationDirectory directoriesYouWantToCompress
{% endhighlight %}

**Step 03**
- After compression you can then move your compressed directory to your Dropbox directory or even you can again **gzip** your tar compressed directory to make it more compressed.

{% highlight bash %}
sudo mv YourCompressedDirectory.tar ~/Dropbox (your dropbox directory)
{% endhighlight }

After moving the directory to Dropbox. Dropbox will automatically start uploading your large data. To run few dropbox commands from command line you can download [this file](https://www.dropbox.com/download?dl=packages/dropbox.py). You can learn from [here](http://www.dropboxwiki.com/tips-and-tricks/using-the-official-dropbox-command-line-interface-cli) about how to use commands of this **dropbox.py** script and do few important task for dropbox.
