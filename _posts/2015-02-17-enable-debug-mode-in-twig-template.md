---
title: Enable Debug mode in Twig Template
layout: single_post
ogDescription: Learn about how to enable debug mode in Twig Template to debug your variables, object. Just add few lines of codes and you are ready to use debug in Twig template
categories: [Networking]
tags: [mikrotik]
---

Sometimes you need to see your variables or object in Twig template before printing it out. So to enable debug mode in twig template system you just need to tweak few settings upon initializing twig environment. Just follow the below code where I initiated Twig environment with debug mode.

{% highlight php %}
$twig = new Twig_Environment($loader, array(
    'debug' => true,
    // ...
));
$twig->addExtension(new Twig_Extension_Debug());
{% endhighlight %}

And inside your template where you want to dump the variable just write `{{ dump(yourVariable) }}`. You can read more about **dump** function twig template from [here](http://twig.sensiolabs.org/doc/functions/dump.html)
