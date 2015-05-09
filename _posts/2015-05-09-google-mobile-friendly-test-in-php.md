---
title: Google Mobile-friendly test in PHP
layout: single_post
ogDescription: Exclusive solutions to check Google Mobile-friendly test in PHP. No API required. Less than 10 lines of code and check your mobile friendly site in PHP
categories: [PHP, SEO]
---

Lots of folks out there about to make your website Mobile-friendly. It's obvious that there will be significant impact on your website if your site is not mobile-friendly or what we regularly call 'responsive'. Mobile friendly sites will [get higher rank](http://googlewebmastercentral.blogspot.com/2015/02/finding-more-mobile-friendly-search.html) in search results in Google. And Google already started to [rolling out this algorithms](http://googlewebmastercentral.blogspot.com/2015/04/rolling-out-mobile-friendly-update.html).

After searching on internet, I didn't get any quick solution to check mobile-friendliness website in PHP. Although Google published it's official [Mobile-friendliness Test Tools](https://www.google.com/webmasters/tools/mobile-friendly/).

When I tried to find some solutions then I figured out that Google has it's public Pagespeed Test API v2. But in this version Google didn't make it clear to see Pass or fail result for mobile-friendliness test. It only shows UX score. But in their **v3beta1** API version they have a clear indicator about mobile-friendliness. And I figured it out and made a simple PHP functions to check the mobile-friendliness test of any website. Here is my scripts:

<script src="https://gist.github.com/shahariaazam/73c0644c6b2f2cba5ca2.js"></script>

In the above script you just need to put your website URL to check and Google PageSpeed API Key what you will get from your [Google API Console](https://code.google.com/apis/console) or see the [Google PageSpeed Developer Getting Starter](https://developers.google.com/speed/docs/insights/v1/getting_started#invoking) page. 

Now, run your script and you will get the following array.

{% highlight php %}
array (size=8)
  'kind' => string 'pagespeedonline#result' (length=22)
  'id' => string 'http://facebook.com/' (length=29)
  'responseCode' => int 200
  'ruleGroups' => 
    array (size=1)
      'USABILITY' => 
        array (size=2)
          'score' => int 100
          'pass' => boolean true
  'pageStats' => 
    array (size=2)
      'numberRobotedResources' => int 0
      'numberTransientFetchFailureResources' => int 0
  'formattedResults' => etc.........
{% endhighlight %}

From the above array `$result['ruleGroups']['USABILITY']['pass']` is the actual result of your website's mobile-friendliness status. true means your website is mobile friendly and false means your failed to make your website mobile friendly. Simple.

Have fun! Write comments if you need any more assistance.
