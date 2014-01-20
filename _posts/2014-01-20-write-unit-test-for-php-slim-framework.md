---
title: Write unit test for Slim Framework
layout: single_post
ogDescription: Useful test class for unit testing of Slim Framework driven PHP application by PHPUnit. Tried to show you preety simple test class however unit testing is tough for slim.
categories: [PHP, Slim Framework]
---
It's not so easy to write **Test Cases** for slim framework. But I tried by autoloading `Slim\Environment` class by requiring applications global `autoload` script.

And after that I just created a Slim mock environment to handle the test case environment.

<script src="https://gist.github.com/shahariaazam/8523437.js"></script>

**If you have any further idea about to please share with me. Thanks in advance!**
