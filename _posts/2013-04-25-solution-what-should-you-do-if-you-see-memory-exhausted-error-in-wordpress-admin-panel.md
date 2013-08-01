---
title: '[Solution] What should you do if you see Memory exhausted error in wordpress admin panel?'
author: admin
layout: single_post
permalink: solution-what-should-you-do-if-you-see-memory-exhausted-error-in-wordpress-admin-panel
categories:
  - Wordpress
tags:
  - how to
  - solution
  - wordpress
---
Recently I faced a very strange (to me) problem with my site that is I can&#8217;t see http://www.shahariaazam.com/wp-admin page. When I go there then I see an error something like &#8220;<span class="hihglight1">Fatal error: Allowed memory size of 33554432?bytes exhausted (tried to allocate 1966080 bytes) in &#8230;..</span>&#8220;. It will make you tensed about that this error. Don&#8217;t worry. I have a solution.

But after lots of searching at last I solved it by my own brainstorming that can be strange. It&#8217;s cause because of your PHP execution memory limit.

If you are using dedicated server then you can just find your php.ini file and find &#8216;memory\_limit&#8217;. You can change this memory\_limit value to something little bigger like 64M, 256M depends on your system.

But if you are using shared hosting then you can just create a new file in your wp-admin directory of your wordpress installation. Rename that new file to php.ini and write the following code.

{% highlight bash %}memory_limit = 256M ;{% endhighlight %}

Now your problem is solved. Now go to yoursite.com/wp-admin and you will be able to access wordpress Dashboard homepage without any error. Happy blogging!!!