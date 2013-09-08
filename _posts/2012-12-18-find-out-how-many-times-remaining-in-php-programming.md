---
title: Find out How Many Times Remaining in PHP Programming
author: admin
layout: single_post
permalink: find-out-how-many-times-remaining-in-php-programming

categories: [PHP]
tags: [PHP, Code]
---
Suppose you have a date 2012-12-20 and today is 2012-12-18. What's the different You can now see the **Time Remaining to 2012-12-18** by implementing the following code.

{% highlight php %}
<?php
    /**
     * @param null $fromTime
     * @param null $toTime
     * @param bool $is_simple
     * @param array $options
     * @return string
     * @copyright     Shaharia Azam 2012-2020, Shaharia Azam Personal Project. (http://shahariaazam.com/)
     * @link          http://shahariaazam.com Personal Project
     * @license       MIT License (http://www.opensource.org/licenses/mit-license.php)
     */
    function TimeAfter($fromTime = null, $toTime = null,$is_simple=true, array $options=array('before'=>false,'after'=>false))
    {
        if(is_array($options)){
            if(array_key_exists('before',$options) && !empty($options['before']))
                $before=$options['before']; else $before="";
            if(array_key_exists('after',$options) && !empty($options['after']))
                $after=$options['after'];   else $after="";
        }
        if (!empty($fromTime) && !empty($toTime))
        {
            $start_date = new DateTime($toTime);
            $since_start = $start_date->diff(new DateTime($fromTime));

            if($is_simple === true)
            {
                if($since_start->m == "0")
                {
                    return $before.$since_start->d." days".$after;
                }
                return $before.$since_start->m." months ".$since_start->d." days".$after;
            }
            else
            {
                if($since_start->Y == "0")
                {
                    return $before.$since_start->m." months ".$since_start->d." days".$after;
                }
                return $before.$since_start->Y." years ".$since_start->m." months ".$since_start->d." days".$after;
            }

        }
    }
{% endhighlight %}

Now you can use `TimeAfter()` with all your required arguments.

To get PHP current date time you can use 
{% highlight php %}
<?php echo date('Y-m-d'); ?>
{% endhighlight %}
To compare with the previous date you can use 
{% highlight php %}
<?php echo $YourDateValue; ?>
{% endhighlight %}
To get simple format you can use the function as follows&#58;

{% highlight php %}
$remaining= TimeAfter(date('Y-m-d'),'2012-12-18',true,array('before'=>'after '));
{% endhighlight %}

Argument List respectively&#58;
<pre>
$fromTime =Your Current Time
$toTime = Comparing Previous Date
$is_simple = default (true) [return simple format data]
$options=array('before'=>'Remaining ', 'after'=>' ');
'before' and 'after' will be placed while returning the final print
</pre>
Happy Coding!!