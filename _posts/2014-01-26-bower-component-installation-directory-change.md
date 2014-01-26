---
title: Bower component installation directory change
layout: single_post
ogDescription: Change the default installation directory of Bower components to user-defined location. Bower is a front-end library dependency management tools.
categories: [Javascript]
---

To change the bower's component installation directory as you want you first need to create a `.bowerrc` file and define the custom location in this `.bowerrc` like the below.

{% highlight json %}
{
    "directory": "yourCustomDirectoryLocation"
}
{% endhighlight %}

Then as usual just make a `bower.json` file where you will write down all the dependencies for your projects like the below.

{% highlight json %}
{
  "name": "YourProjectName",
  "description": "Description of your project",
  "homepage": "http://yourProjectUrl.com/",
  "author": "Yourname <your@email.com>",
  "dependencies": {
      "bootstrap":">= 3.0.0",
      "jquery": "~2.0.3"
  }
}
{% endhighlight %}

now run `bower install` command and all the required dependencies will be installed to your defined directory (as you configured in your .bowerrc file).
