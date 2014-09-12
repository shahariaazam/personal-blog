---
title: Backup windows server with ssh or ftp
layout: single_post
ogDescription: Backup your windows server and store backup to remote via ssh or ftp connectiontivity. Complete tips of taking backup and upload on remote.
categories: [Windows Server]
---

Typically windows server has no built-in backup transfer system via SSH or FTP/SFTP. They can only take backup and transfer to another windows machine. But in the age of cloud computing we need portablity of data. Anywhere I can put or get data.

So from this sense I tried to get some handy tools which will do a perfect trick for me. For my windows server I love **rsync** very much. It's lovely. I like it's awesomeness. Also for windows server backup [rsync](http://www.rsync.net/) has a great windows backup client which did my job perfectly without any non-sense hassle.

Just go to [rsync windows backup client download page](http://www.rsync.net/resources/howto/windows_backup_agent.html) and [download](http://www.rsync.net/resources/binaries/backup_agent_6.65.exe) the tools. Install it and start using it.

Here is the easy backup profiling screenshot of rsync windows backup client.
![windows server backup tools](http://www.rsync.net/images/agent_wizardr.jpg)
