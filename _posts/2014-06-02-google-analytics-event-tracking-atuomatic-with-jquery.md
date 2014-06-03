---
title: Google analytics event tracking with jQuery automatically
layout: single_post
ogDescription: Learn how to track custom event for your website or web application with google analytics custom event tracking
categories: [Analytics, Tracking]
---

It's easy to track the user behavior from your web application or webpages like you can track where your user is clicking, what are they doing, etc.... with the help of Google analytics custom event tracking.

{% highlight javascript %}
<script>
$(document).ready(function(){
        $('a').on('click', function() {
            var anchorText = $(this).text();
            var anchorUrl = $(this).attr('href');

            ga('link', 'click', anchorText, anchorUrl);
        });
    })
</script>
{% endhighlight %}

In the above code I am just triggering `ga()` function (analytics function provided by Google analytics js script) when anyone will click any link in the whole documents. Then when user will click on any link (anchor text) then the `ga()` function will be triggered with my custom url, action, text value.

So from now on you can get this report from [Google analytics](http://www.google.com/analytics).
