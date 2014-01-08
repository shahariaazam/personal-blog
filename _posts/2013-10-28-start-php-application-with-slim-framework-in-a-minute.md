---
title: Start PHP application with Slim Framework in a minute
layout: single_post
ogDescription: Learn how to build an environment to develop a PHP application with Slim framework in a minute to get started for production.
categories: [nginx, PHP, slim]
tags: [php, slim]
---

I am using **nginx** server for this documentation.

First of all just choose a directory where you are gonna keep all your appliction files. Suppose, _/var/www_ is going to be that directory.
Create a directory and rename it with **yourapplication-name**. Inside that directory just create few pre-planned directory and file structure like the following.

<pre>
  │   ├── routes
  	  ├── src
  	  ├── utilities
  	  ├── public
  	  		├── img
  	  		├── js
  	  		├── css
  	  		├── index.php
  	  ├── templates
  	  ├── composer.json

</pre>

We will manage and install all the dependencies by our `composer.json`. And now let's write which thins is gonna be used for our project and write down that in our **composer.json** file like following.

{% highlight json %}
{
    "name": "Project Name",
    "description": "Project description",
    "homepage": "Project URL",
    "authors": [
        {
            "name": "Your name",
            "email": "youremail@email.com"
        }
    ],
    "require": {
        "php": ">=5.3.0",
        "slim/slim": "dev-master",
        "slim/views": "0.1.*"
    },
    "autoload": {
        "psr-0": {
            "": "src/"
        }
    }
}
{% endhighlight %}

Now we need to run this composer. To install the above dependencies just run the following commands.

{% highlight bash %}
$ cd /var/www/yourapplicationdirectory
$ php composer.phar install
{% endhighlight %}

If you haven't `composer.phar` installed on your machine then just [install it](http://getcomposer.org/doc/00-intro.md#installation-nix) before running the above commands.

Now your project has all dependecies ready and it's time to code inside your `public/index.php`.

For Slim Framework you can test your installation by writing the following code in your `public/index.php` file.

{% highlight php %}
<?php
require '../vendor/autoload.php';
\Slim\Slim::registerAutoloader();
$app = new \Slim\Slim();
$app->get('/hello/:name', function ($name) {
    echo "Hello, $name";
});
$app->run();
{% endhighlight %}

Ohh yes, I forget to tell you about the **nginx** configuration for your application.

Just open nginx configuration file from **/etc/nginx/sites-available/default** and add the following default configuration in that file and restart nginx. You're done.

{% highlight apacheconf %}
server {
        listen       80;
        server_name  yourapplication-name.dev;
        root /var/www/yourapplication-name/public/;

        access_log /var/log/nginx/yourapplication-name.access.log;
		error_log  /var/log/nginx/yourapplication-name.error.log;

        location / {
            index index.php;
            try_files $uri $uri/ /index.php?$args;
        }

        location ~ \.php/?(.*)$ {
    
            fastcgi_connect_timeout 3s;     # default of 60s is just too long
            fastcgi_read_timeout 10s;       # default of 60s is just too long
   
            fastcgi_pass unix:/var/run/php5-fpm.sock; 
            fastcgi_index  index.php;
    
            include fastcgi_params;
    
            fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        }
	#Access phpmyadmin
	location /phpmyadmin {
	    root /usr/share/;
	    index index.php index.html index.htm;
	    location ~ ^/phpmyadmin/(.+\.php)$ {
		try_files $uri =404;
		fastcgi_pass   unix:/var/run/php5-fpm.sock;
		include fastcgi_params;
	    }
	}

}
{% endhighlight %}

Now change your hostname from **/etc/hosts** and add `127.0.0.1 yourapplication-name.dev`. And now restart your network by **$ sudo /etc/init.d/networking/restart** and also restart nginx.
After that now open your browser and type **yourapplication-name.dev/hello/yourname** you can see `hello yourname` printed there.

Happy coding.