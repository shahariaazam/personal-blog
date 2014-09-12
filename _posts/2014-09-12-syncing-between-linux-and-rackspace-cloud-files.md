---
title: Syncing between Linux and Rackspace Cloud Files
layout: single_post
ogDescription: Tutorial on tools to syncronize between Linux PC and Rackspace Cloud Files in a best and easy way. Learn how to backup files from Linux to Rackspace Cloud Files
categories: [Ubuntu, Cloud Server]
---

Whole the night I was struggling to build a safe house for my codes where my codes can live longer safely. Sounds funny? Yes, it is. So whenever you or I think about to build a safe place to host our codes then first priority we consider about Backup and Restoring files with less hassle. And today I figured our a very sophisticated way about to handle synchronizing or backup/restore your files between your Linux flavor computer and [Rackspace Cloud Files](http://www.rackspace.com/cloud/files/).

In my research case I had one cloud server on Rackspace. That server was powered by Ubuntu Server 14.04 LTS. I usually use Rackspace Cloud Files to keep my backup files on cloud so I can easily use them. So I wanted to figure our a very simple way to handle the backup which will automatically take backup and store those backups to Rackspace Cloud Files.

Suddenly for God's sake I got a link in [Rackspace forum](http://www.rackspace.com/knowledge_center/article/syncing-to-cloud-files-with-fileconveyor) that was about [FileConveyor](http://fileconveyor.org/). OMG! This tools really works amazing. So I can easily upload backup from my cloud server to Rackspace Cloud Files with this life saving FileConveyor. 

Here is the process to install FileConveyor in your server or personal Linux flavor computer.

- First you have to install Git with **sudo apt-get install git**
- You must have to install Python and [Python Package Manager](https://pypi.python.org/pypi/setuptools#unix-wget). To install python Package Manager you have to run this command `wget https://bootstrap.pypa.io/ez_setup.py -O - | sudo python`.
- After installing Pythin Package Manager you can use **easy_install** command. And now install **pip** with this `easy_install` command like `sudo easy_install pip`
- Now choose where you want **FileConveyor** files by using cd command. And then run this `sudo pip install -e git+https://github.com/wimleers/fileconveyor@master#egg=fileconveyor` command. So you will get all the required python files for [fileconveyor from GitHub](https://github.com/wimleers/fileconveyor).
- Now it's time to write your own `config.xml` files for this tools. Now need to create this config.xml file and write the following XML content inside that file with this command `sudo vi src/fileconveyor/fileconveyor/config.xml` with the following content.

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<config>
  <!-- Sources -->
  <sources ignoredDirs="">
    <source name="test" scanPath="/var/www/html/test" />
  </sources>

  <!-- Servers -->
  <servers>
    <server name="Rackspace Cloud Files" transporter="cloudfiles">
      <username>USERNAME</username>
      <api_key>APIKEY</api_key>
      <container>CONTAINER</container>
    </server>
  </servers>
 <!-- Rules -->
  <rules>
    <rule for="test" label="Test">
      <destinations>
        <destination server="Rackspace Cloud Files" path="test" />
      </destinations>
    </rule>
  </rules>
</config>
{% endhighlight %}

You'll need to modify the config to fit your environment and account details.

In the "Sources" section change the "scanPath" property to the directory you want to sync.
In the "Servers" section set "username" and "api_key" to match your credentials, and set "container" to the name of the container to hold the synced files.
In the "Rules" section set the "path" property to the subdirectory to sync to in the container. Leave the value blank to sync to the root of the container (path="").

Now run this awesome tools with this `sudo python src/fileconveyor/fileconveyor/arbitrator.py` command.

_**Note:** If you see any error like Transport class not found or something related to transport class then please install **django-cumulus==1.0.10** package with this command `pip install django-cumulus==1.0.10`. Now again run FileConveyor and it will start syncing_. 
It's cool! huh? Of course it will save you from losing life for codes.
