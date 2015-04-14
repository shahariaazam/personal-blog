---
title: Twig and AngularJS curly braces conflict solution
layout: single_post
ogDescription: Learn how to implement AngularJS within your Twig template engine. Easy solution. Let's work together with AngularJS and Twig for better UI
categories: [AngularJS, Twig]
---

Whoever loves to work with (Twig template system)[http://twig.sensiolabs.org/] for their PHP driven web application may want to implement (AngularJS)[https://angularjs.org/] within Twig template. But the main problem will be Twig's curly braces. AngularJS and Twig both use **{{ }}** inside their template to output data. So simply, it can cause trouble to work with this two lovely systems together in your application.

But here is the solution. According to (AngularJS $interpolateProvider)[http://docs.angularjs.org/api/ng.$interpolateProvider] docs I figured out the easy solution. You can change AngularJS **{{ }}** symbol with any other symbol. Cool! So see how you will override that configuration.

{% highlight js %}
var app = angular.module('myApp', []);

app.config(function($interpolateProvider){
  $interpolateProvider.startSymbol('{[{').endSymbol('}]}');
});
{% endhighlight %}

Now you can use **{[{ }]}** symbol for your AngularJS. And Twig use **{{ }}**. So problem solved. From now on you can use AngularJS within your Twig template system.
