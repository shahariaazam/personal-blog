---
title: AngularJS Resource use for RESTful apps
layout: single_post
ogDescription: Learn how to use ngResource service with AngularJS for RESTful apps. This example script will help you to solve that.
categories: [AngularJS]
---
This example will help you to learn how to interact between your backened RESTful apps and AngularJS. AngularJS has a service factory called [ngResource](https://docs.angularjs.org/api/ngResource) which you can use to do CRUD operation with your RESTful backend application.

Here you just need to define the service factory which will get all notes by calling an ajax request to your **http://yourRESTAPIBackendserver.url/notes**. Also you can do rest of the CRUD services with that script. This script represents very basic usage of **ngResource**. So you learn it and try to DYI.

<script src="https://gist.github.com/shahariaazam/3e0cb39cc4908876b1f3.js"></script>

Don't forget to add the main angularjs library and ng resource service library in your html head tag.

{% highlight %}
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.15/angular.min.js"></script>
<script src="https://code.angularjs.org/1.2.0-rc.2/angular-resource.js"></script>
{% endhighlight %}
