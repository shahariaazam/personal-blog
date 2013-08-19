---
title: Few easy example of PHP Data Type
layout: single_post
ogDescription: Data type is a very important chapter of PHP programming language. Learn PHP Data Type by seeing few example from this post.
categories: [PHP]
tags: [PHP, Data Type]
---

There are 8 types of Data in PHP programming language. Here is the list of all **Data Types**&#58;
#####Scalar Type
	1.	Boolean
	2.	Integar
	3.	Float
	4.	String

#####Compound Type
	5.	Array
	6.	Object

#####Special Type
	7.	Resource
	8.	Null

Now please see the following code and run yourself on your computer to see the result and I hope you will easily understand about what is PHP `Data Type` and the usage of this.

{% highlight php %}
<?php
/**
 *  @Author: G. M. Shaharia Azam
 *  @URL: http://www.shahariaazam.com
 *  @Description: Few example of PHP Data Type
 */

/*  delcare few variable to check their data type */
$intVar = 10;   //Integar variable

$floatVar = 2.49;   //Float type aka Double

$stringVar = "There are 8 data types in PHP";   // String

$arrayVar = array(
    'Boolean', 
    'Integar', 
    'Float aka Double',
    'String', 'Array',
    'Object',
    'Resource',
    'Null'
);  // Array type

$booleanVar = true; // Boolean type

// Make an empty class to check object type
class obj{

}

$objectVar = new obj();

// To check resource type
$resource = mysql_connect();

// Null value
$nullVar = null;

// output the data type of each variable
echo gettype($intVar);
echo "\n";
echo gettype($floatVar);
echo "\n";
echo  gettype($stringVar);
echo "\n";
echo gettype($arrayVar);
echo "\n";
echo gettype($booleanVar);
echo "\n";
echo gettype($objectVar);
echo "\n";
echo gettype($resource);
echo "\n";
echo gettype($nullVar);
echo "\n";
{% endhighlight %}

Write down your comments if you face any problem regarding PHP Data Type. Happy PHP-ing.