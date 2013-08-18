---
title: Install Sublime Text 2 on Ubuntu and make application shortcut luncher
layout: single_post
ogDescription: See how to install Sublime Text 2 on Ubuntu and make application luncher. The best lightweight editor for programmers. Try it and you will love it. Happy coding!
categories: [IDE]
tags: [Editor, IDE, Sublime Text, Ubuntu]
---
#####Step 1
Download Sublime Text 2 from their download location. To download it please type the following command &#58;

{% highlight bash %}
sudo wget http://c758482.r82.cf2.rackcdn.com/Sublime%20Text%202.0.2.tar.bz2
{% endhighlight %}

#####Step 2
After downloading **Sublime Text 2** you'll need to extract the `.tar.bz2` file. To extract `tar.bz2` type the following command &#58;

{% highlight bash %}
tar xf Sublime\ Text\ 2.0.1\ x64.tar.bz2
{% endhighlight %}

Now you will get a extracted directory with all the files needed to run `Sublime Text 2`. So it's better to move this directory to another appropriate place. To move this folder

{% highlight bash %}
sudo mv Sublime\ Text\ 2 /opt/
{% endhighlight %}

If you want to write `sublime` command only to run `Sublime Text 2` then you need to link the file by typing the following command &#58;

{% highlight bash %}
sudo ln -s /opt/Sublime\ Text\ 2/sublime_text /usr/bin/sublime
{% endhighlight %}

Now to create luncher in Ubuntu Unity we just need to create `sublime.desktop` file in **/usr/share/applications** with the following snippet &#58;

Create `sublime.desktop` file by typing the following command &#58;
{% highlight bash %}
sudo sublime /usr/share/applications/sublime.desktop
{% endhighlight %}

Then write the following code in newly created blank text file.

{% highlight bash %}
[Desktop Entry]
Version=1.0
Name=Sublime Text 2
# Only KDE 4 seems to use GenericName, so we reuse the KDE strings.
# From Ubuntu's language-pack-kde-XX-base packages, version 9.04-20090413.
GenericName=Text Editor

Exec=sublime
Terminal=false
Icon=/opt/Sublime Text 2/Icon/48x48/sublime_text.png
Type=Application
Categories=TextEditor;IDE;Development
X-Ayatana-Desktop-Shortcuts=NewWindow

[NewWindow Shortcut Group]
Name=New Window
Exec=sublime -n
TargetEnvironment=Unity
{% endhighlight %}

Save this file and restart your terminal. And type the following command to run `sublime`.

{% highlight bash %}
sudo sublime
{% endhighlight %}

Now enjoy the power of the world's most popular editor for programmers. Happy coding!