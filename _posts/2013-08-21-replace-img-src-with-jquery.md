---
title: Replace img src with jQuery
layout: single_post
ogDescription: Learn how to replace any src attribute of img tag with jQuery. Pretty simple and do it with 2 line jquery code.
categories: [HTML, JQuery]
tags: [codes, snippet, tricks, tips]
---

Simple we use to show a image by writing the following code&#58;
{% highlight html %}
<img src ="thelocationofyourimage.jpg" >
{% endhighlight %}

Now if sometime you need to change this `src` attribute value by `jQuery`. Then you need to put down the following code. 
{% highlight js %}
$('img[src^="thelocationofyourimage.jpg"]').each(function() {
   $(this).attr('src', $(this).attr('src').replace("thelocationofyourimage.jpg", "UpdatedLocationOfTheImage.jpg"));
});
{% endhighlight %}

Try it by yourself. Thanks in advance.