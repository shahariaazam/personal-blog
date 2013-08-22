---
title: How to Install Ruby on Rails in your Localhost
author: admin
layout: single_post
permalink: how-to-install-ruby-on-rails-in-your-localhost

categories: [Ruby on Rails]
tags: [rails, ruby gems]
---

This is pretty much a big question for you who want to work in <a title="Official website of Ruby on Rails" href="http://rubyonrails.org" target="_blank">Ruby on Rails</a>. Now I am writing this tutorial for you to install Ruby on Rails in your Localhost to start coding on Rails framework.

# Installing Ruby on Rails

To install ruby on Rails in your localhost you need the following things.

*   Ruby > <a title="Download Ruby" href="http://rubyforge.org/frs/?group_id=167" target="_blank">Download</a>
*   Ruby Gems > <a title="Download Ruby Gems" href="http://rubygems.org/pages/download" target="_blank">Download</a>
*   Ruby Development Kit > <a title="Ruby Development Kit" href="http://rubyinstaller.org/downloads/" target="_blank">Download</a>
*   Rails > Install from command line

After downloading Ruby from the above mentioned link then you will have to double click the installer file and press next next next and finish the installation. It&#8217;s the pretty simpler process to install Ruby on your PC.

Then also Install Ruby Development Kit by clicking. Then from your Command prompt window just use cd and go to your devkit directory. and write
{% highlight ruby %}
ruby dk.rb init
{% endhighlight %}
then it will bind with main ruby installation.

Then you need to download the latest version of Ruby Gems. It&#8217;s the standard Ruby package manager.

Then you need to open your Command Line Prompt and type

{% highlight ruby %}
gem install rails
{% endhighlight %}

It will take few minutes to complete installing Ruby Gems. Â Now it&#8217;s done!! Now you can [create Rails project][1] and run it from your own PC.

 [1]: http://www.shahariaazam.com/create-ruby-on-rails-project-and-start-rails-server-on-localhost "Create Ruby on Rails Project and run in Localhost"