---
title: How to Ping to a Server in PHP
layout: single_post
permalink: how-to-ping-to-a-server-in-php
categories: [PHP]
tags: [PHP, Code, Tips, Tricks]
---

Sometimes we need to check whether any specific server are up or down. It's sometimes so much important. So that I have prepared the following code snippet which will tell you about the server whether it is down or up.

I have used fSockOpen in this case to test it. so the function I have created is 
{% highlight php %}
<?php
/**
 * @param null $host
 * @param null $port
 * @param null $timeout
 * @return bool|string
 */
function PingToServer($host=null, $port=null, $timeout=null)
{
    if(empty($host) || empty($port) || empty($timeout)){
        return false;
    }
    $TimeStart = microtime(true);
    $Response = fSockOpen($host, $port, $errno, $errstr, $timeout);
    if (!$Response) { return "down"; }
    $TimeEnd = microtime(true);
    return round((($TimeEnd - $TimeStart) * 1000), 0)." ms";
}
PingToServer("www.google.com",80,10)
{% endhighlight %}
Here **www.google.com** is the hostname or server address, 80 is the port number to check and 10 is the timeout period.

Happy coding!!