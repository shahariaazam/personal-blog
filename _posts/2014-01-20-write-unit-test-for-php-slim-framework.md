---
title: Write unit test for Slim Framework
layout: single_post
ogDescription: Useful test class for unit testing of Slim Framework driven PHP application by PHPUnit. Tried to show you preety simple test class however unit testing is tough for slim.
categories: [PHP, Slim Framework]
---
It's not so easy to write **Test Cases** for slim framework. But I tried by autoloading `Slim\Environment` class by requiring applications global `autoload` script.

And after that I just created a Slim mock environment to handle the test case environment.

{% highlight php %}
<?php
 
require_once __DIR__ . '/../vendor/autoload.php';
 
use Slim\Environment;
 
 
class RoutesTest extends PHPUnit_Framework_TestCase
{
 
    public function request($method, $path, $options = array())
    {
        // Capture STDOUT
        ob_start();
 
        // Prepare a mock environment
        Environment::mock(array_merge(array(
            'REQUEST_METHOD' => $method,
            'PATH_INFO' => $path,
            'SERVER_NAME' => 'slim-test.dev',
        ), $options));
 
        $app = new \Slim\Slim();
        $this->app = $app;
        $this->request = $app->request();
        $this->response = $app->response();
 
        // Return STDOUT
        return ob_get_clean();
    }
 
    public function get($path, $options = array())
    {
        $this->request('GET', $path, $options);
    }
 
    public function testIndex()
    {
        $this->get('/');
        $this->assertEquals('200', $this->response->status());
    }
}
{% endhighlight %}

**If you have any further idea about to it please write it down.**
