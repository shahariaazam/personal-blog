---
title: Deploy and update codes from Github repo in PHP
layout: single_post
permalink: deploy-and-update-codes-from-github-repo-in-php
ogDescription: Learn how to deploy Github repo in your server by using your simple PHP script and Github Service Hooks. Easy and most important things for PHP programmers.
categories: [Github, PHP]
tags: [Git, php, deploy]
---

Sometimes it is pretty important for programmers to auto deploy the latest Git repositories to update the local source codes in development server or live project server. After researching lots of easy and complex resource I found some pretty easy techniques to do that things in few minutes. Let's see how we can accomplish this task which can save our big time.
	*in this article I used Ubuntu 12.04 Server OS and GitHub as code hosting platforms *

#####Step 01 - Create your Git repository
From [https://github.com/new](https://github.com/new) create your GitHub repository.
![Create public git in GitHub](/assets/img/public/create-public-git-in-github.png)

#####Step 02 - Create local (server machine) git repo and Push to github repo

Now create you local (server machine) git repo to push that initial files to github repo

{% highlight bash %}
sudo mkdir deploy-git-php-tutorial
cd deploy-git-php-tutorial
touch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/shahariaazam/deploy-git-php-tutorial.git
git push -u origin master
{% endhighlight %}

Now you did initially push to your `https://github.com/shahariaazam/deploy-git-php-tutorial.git` repo.

**We want to accomplish that when we will push code to that repository then our server will pull the latest update from that repo** isn't it? Of course YES!

#####Step 03 - Configure GitHub Service Hooks
You already pushed your first commit to the repo. Now go to [https://github.com/githubusername/deploy-git-php-tutorial/settings/hooks](https://github.com/githubusername/deploy-git-php-tutorial/settings/hooks) to set **WebHook URLs** (WebHook URLs means when you will push anything to your repo then github will send few data as a POST request to this WebHook URLs. It will actually did our main job). We will set an URL here so when we will push to the git then github will call this URL (our php script will execute while github post request will be made). And we will write down our tricks in that PHP script to update our web server's codes.

For example we want to update codes of **http://cloud.shahariaazam.com/deploy-git-php-tutorial** from latest github repository. So we have to create a `pull.php` so that our WebHook url will look like `http://cloud.shahariaazam.com/deploy-git-php-tutorial/pull.php`.
![Add Service hook url in Github](/assets/img/public/add-github-service-hooks.png)

#####Write codes to your script to update your local codes
So that we have to write down our logic in our `pull.php` script in our server that will execute and update the local repo when we will push something to our git and github will post data to this `http://cloud.shahariaazam.com/deploy-git-php-tutorial/pull.php`.

I did few simple code in our `pull.php` script like the following.

{% highlight php %}
<?php
// write few logic to make strong security
exec('git pull');
{% endhighlight %}

You can think that I am gonna crazy because of direct use of `exec()` function. But believe me you can make few strong security to make it more secured to run this command. You can check whether it is coming from github or not or restricted it with few secret key or anything whatever you can find out by browsing your brain. lol.  I just made it to test myself with simple techniques. I didn't yet use it for any of my real-life project. But I will surely do few security checkup before executing this `exec()` function. Please don't tell me *fool* &#58;P.

#####Check the result
Now all done! Now you need to test the result by yourself. To see the result you have to push something to your git. And when you will push something to your git by using `git push` command then GitHub will trigger your previously mentioned WebHook URL and your script will run the `git pull` command and your local repository will be updated.

Now make a new file like `test.php` with any sample code to test.
{% highlight php %}
#create a file test.php and write something like echo 'hello world' in that file and push to github
sudo vim test.php
git add test.php
git commit -m "test commit"
git push -u origin master
{% endhighlight %}

Now you have pushed something to your git from your local PC. Now just from your browser go to `http://yourserverurl.com/test.php` in this case I used `http://cloud.shahariaazam.com/deploy-git-php-tutorial/test.php` then you will see that your latest push'ed code has been update to your remote working server and `test.php` is outputting *hello world*. 

	The whole process will be done automatically each time when you will push something to your repo. 

Now you can work from anywhere (your personal machine, server machine) to push to that repo by `https://github.com/shahariaazam/deploy-git-php-tutorial.git` command and after changing something whenever you will push your server repo will be updated.

Write your comments in this article if you have any question, suggestions. Happy coding!