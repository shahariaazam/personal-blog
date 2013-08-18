---
title: Assign Sublime Text 2 to open all text file on Ubuntu
layout: single_post
ogDescription: Open all text file of Ubuntu in the most popular text editor Sublime Text 2 editor. Quick solution and tips. Just do and enjoy coding.
categories: [Editor]
tags: [Ubuntu, Sublime Text]
---

To open all `text file` of Ubuntu with the most popular text editor **Sublime Text 2** you just need to do the following job.

First type the following command &#58;

{% highlight bash %}
sudo sublime /usr/share/applications/defaults.list
{% endhighlight %}

*Make sure that you can run `Sublime Text` by typing just `sublime` command in terminal. If this hasn't configured yet. Just [see this post](http://blog.shahariaazam.com/install-sublime-text-2-on-ubuntu-and-make-application-shortcut/) about how to install Sublime Text 2, make luncher and make command in terminal.*

Now after opening the **defaults.list** file just replace all occurrences of **gedit.desktop** with **sublime.desktop**. Now all of your text file will open in Sublimte Text editor.