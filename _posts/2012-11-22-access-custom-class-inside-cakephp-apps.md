---
title: Access Custom Class inside CakePHP Apps
layout: single_post
permalink: access-custom-class-inside-cakephp-apps
categories: [PHP, CakePHP, OOP]
tags: [php, cakephp, tutorial, tips, OOP]
---
If you have ever made any PHP Classes for your work. Then it&#8217;s pretty easy to add those classes inside your CakePHP driven application. You need to follow the below steps.

*	Steps 1:
	You first have to place a class file inside a directory

*	Steps 2:
	Then open App/Config/bootstrap.php from your CakePHP application directory and write the following codes.

{% highlight php %}
//mydir is another directory placed outside of cakephp directory
App::build(array(
    'GlobalUsers' => array(dirname(CAKE_CORE_INCLUDE_PATH).DS.'mydir'.DS)
), App::REGISTER);
{% endhighlight %}

It will just add the location to your CakePHP apps.

*	Now in your active working CakePHP directory just open AppController.php file and add your newly added class. 
{% highlight php %}
App::uses('UsersController','GlobalUsers');
{% endhighlight %}

In the above code here UsersController is your file name like **UsersController.php**

Now you can access your *classes* inside *UsersController.php*

Have coding with CakePHP.