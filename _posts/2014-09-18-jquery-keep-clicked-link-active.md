---
title: Keep navigation link active with jQuery
layout: single_post
ogDescription: Keep your HTML link active in jQuery when people will click on that and visit that page.
categories: [Windows Server]
---

After clicking on any navigation link in navgation and whenever that page will be open then one active class will be added in that element.

{% highlight javascript %}
$(document).ready(function(){
 var a = $('.navbar-nav a');
 a.each(function(){
   if(window.location.href == $(this).attr('href')){
     $(this).closest('li').addClass('active');
   }
 })
})
{% endhighlight %}
