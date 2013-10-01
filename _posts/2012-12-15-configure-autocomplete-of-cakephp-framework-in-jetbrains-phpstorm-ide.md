---
title: Configure AutoComplete of CakePHP framework in JetBrains PHPStorm IDE
layout: single_post
permalink: configure-autocomplete-of-cakephp-framework-in-jetbrains-phpstorm-ide

categories: [PHP]
tags: [Tags, CakePHP, PHP]
---
I am a fan of CakePHP Framework and PHPStorm IDE. But since longs times I tried to setup autocomplete of cakephp MVC structure code in PHPStorm but I failed. But from now I can do that and my development is now being more fast. Let's try it yourself too!!

Inside your Controller inside each script to get Model's autocomplete suggestion just put the following comments- 
*(i.e in YoursController.php file just put the following comments at the top)*
{% highlight php %}
<?php
/**
 * @property User $User
 */
{% endhighlight %}

In the above code `User` is the model property. So from now you can get the User model's autocomplete suggestion.

Now inside your View file `YourViewFile.ctp` you just put the following code-

{% highlight php %}
<?php
/**
 * @var $this View
 */
?>
{% endhighlight %}
Here you are going to see all `View/Helper`'s autocomplete suggestion suppose when you will write `$this->Html->` then `ctrl+space` and you will see all the suggestion there.

I hope it will help all the CakePHP lovers and PHPStorm users a super fast programming environment. Happy coding!!