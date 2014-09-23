---
title: Create PhpStorm luncher and terminal command on Ubuntu
layout: single_post
ogDescription: Create PHPStorm one-click luncher on Ubuntu and shortcut terminal command to run PhpStorm PHP IDE more quickly. Easy steps. Learn how to create luncher and enjoy PHP coding with Jetbrains PhpStorm on Ubuntu.
categories: [Editor]
tags: [PhpStorm, Editor, Ubuntu]
---
To run PhpStorm with only `sudo phpstorm` you just need make a direct link to the **phpstorm.sh** executable file.

{% highlight bash %}
sudo ln -s /opt/PhpStorm-121.390/bin/phpstorm.sh /usr/bin/phpstorm
{% endhighlight %}

In the above code `/opt/PhpStorm-121.390/bin/phpstorm.sh` is your PhpStorm's phpstorm.sh executable file location and **phpstorm** word from `usr/bin/phpstorm` this is the assigned command to run PHPStorm IDE from your terminal.

Now to create luncher in Ubuntu Unity we just need to create `phpstorm.desktop` file in **/usr/share/applications** with the following snippet &#58;

Create `phpstorm.desktop` file by typing the following command &#58;
{% highlight bash %}
sudo gedit /usr/share/applications/phpstorm.desktop
{% endhighlight %}

Then write the following code in newly created blank text file.

{% highlight bash %}
[Desktop Entry]
Version=5.0.4
Name=JetBrains PhpStorm
# Only KDE 4 seems to use GenericName, so we reuse the KDE strings.
# From Ubuntu's language-pack-kde-XX-base packages, version 9.04-20090413.
GenericName=Text Editor

Exec=phpstorm
Terminal=false
Icon=/opt/PhpStorm-121.390/bin/webide.png
Type=Application
Categories=TextEditor;IDE;Development
X-Ayatana-Desktop-Shortcuts=NewWindow

[NewWindow Shortcut Group]
Name=New Window
Exec=phpstorm
TargetEnvironment=Unity
{% endhighlight %}

Save this file and restart your terminal. And type the following command to run **PhpStorm**.

{% highlight bash %}
sudo phpstorm
{% endhighlight %}

Happy PHP-ing.
