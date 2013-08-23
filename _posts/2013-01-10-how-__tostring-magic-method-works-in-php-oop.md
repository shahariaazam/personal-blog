---
title: How __toString magic method works in PHP OOP
author: admin
layout: single_post
permalink: how-__tostring-magic-method-works-in-php-oop

categories: [PHP]
tags: [PHP, OOP]
---
`__toString` magic method in PHP OOP is a very good stuff to covert your object into string. Let's write some code without `__toString()`.

{% highlight php %}
<?php
class LearnToString{
    public $WhatIsToString;
    function __construct($WhatIsToString){
        $this->WhatIsToString=$WhatIsToString;
    }
}
$obj=new LearnToString('hello world');
echo $obj;
?>
{% endhighlight %}

Now if you want to see the result then you must see the following error like it says.

{% highlight xml %}
Warning (4096): Object of class LearnToString could not be converted to string [YourFileName.php, line 11]
{% endhighlight %}

Yes, if you are a PHP OOP learner then you should face this error multiple time and it takes few time to search about this in Google. But it's pretty common things while you will spend time on learning PHP OOP. Just now I will use a PHP OOP magic methods `__toString()` in this class. So that when you will make object then it will output you the result as string converted itself. Now let's see what can be the code.

{% highlight php %}
<?php
class LearnToString{
    public $WhatIsToString;
    function __construct($WhatIsToString){
        $this->WhatIsToString=$WhatIsToString;
    }
    function __toString(){
        return $this->WhatIsToString;
    }
}
$obj = new LearnToString('hello world');
echo $obj;
?>
{% endhighlight %}

now you will see that I have used function `__toString()` magic method. Now run the file and you will see `hello world` without any error and that is the power of this `__toString` magic method of PHP OOP. Happy coding!!