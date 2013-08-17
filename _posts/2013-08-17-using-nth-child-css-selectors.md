---
title: Using nth-child CSS selctors
layout: single_post
ogDescription: Learn how to use nth-child CSS selectors for designing your HTML document and make your site more interactive and user-friendly. No javascript required. CSS can do this job. Read it and learn how to use it.
categories: [CSS, Web Development]
tags: [CSS, Web Development]
---

####What is nth-child CSS Selectors&#63;
To select any element inside your `DOM (Document Object Model)` there are lots of CSS selectors. And **nth-child** is one of them, more smarter, handy and useful to use.

By `nth-child` you can select any `*th (1st, 2nd, 3rd, 4th........nth)` element of your HTML DOM. Let's see how we can use it&#58;

####Usage of nth-child in CSS
`nth-child` pseudo&#45;selector define the number-th of your targetted element.
i&#46;e&#58; You have a list item like the following &#58;

{% highlight html %}
<ul>
    <li>First list item</li>
    <li>Second List Item</li>
    <li>Third List Item</li>
    <li>Fourth List Item</li>
    <li>Fifth List Item</li>
    ------------------------
    ------------------------
    <li>n-number List Item</li>
</ul>
{% endhighlight %}

In the above `HTML` code snippet there is total `5` `<li>` elements. Generally to select all `<li>` element we used &#45;

{% highlight css %}
li{
    color: red;
}
{% endhighlight %}

*The above code will make all text inside `<li>` element in red color* But **what you should do if you want to format only 3rd or 5th or 4th element?** In this case we will use our magic CSS pseudo-selector `nth-child`.
<br>
**Output:**
![](/assets/img/public/nth-child-css-usage.png)
<br>
 Let&#39;s assume we will make the color of 4th `<li>` element red. To accomplish this task we need to write the following CSS &#58;

 {% highlight css %}
 li:nth-child(4){
    color: red;
 }
 {% endhighlight %}

 **The above code will make red color to the 4th `<li>` element**

<br>
**Output:**
![](/assets/img/public/2nd-example-nth-child-css.png)
<br>

 Also if you want to select all `odd`&#40;th&#41; number of `<li>` element then you need to write &#45;

 {% highlight css %}
 li:nth-child(odd){
    color: red;
 }
 {% endhighlight %}

 the above code will make red color to 1st&#44; 3rd and 5th `<li>` element. In the same way you can also select all `even` element to select 2nd and 4th `<li>` element with the following CSS code snippet.
 <br>
 **Output:**
 ![](/assets/img/public/3rd-example-nth-child-css.png)
 <br>

 {% highlight css %}
 li:nth-child(even){
    color: red;
 }
 {% endhighlight %}

<br>
**Output:**
![](/assets/img/public/4th-example-nth-child-css.png)
<br>

 Also you can provide any equation as argument for `nth-child` selector. Suppose we will select `3n+1`&#40;th&#41; `*<li>*` element from our above HTML code. Then we need to write the following CSS &#58;

  {% highlight css %}
  li:nth-child(3n+1){
     color: red;
  }
  {% endhighlight %}

  *note&#58; where n &#61; 0&#44; 1&#44; 2&#44; 3&#44; &#46;&#46;&#46;&#46;&#46;&#46; *

  So in that above CSS code our `(3n+1 = 1*st*)` element will be red color. Cause the value of `n` starts from `Zero`. So that `3x0 + 1 = 1` for first element and `3x1 + 1 = 4` for 4th element.. this will continue like this.

  ![](/assets/img/public/5th-example-nth-child-css.png)

  Now it's time to try it yourself!!