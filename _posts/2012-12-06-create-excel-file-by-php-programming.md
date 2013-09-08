---
title: Create Excel File by PHP Programming
layout: single_post
permalink: create-excel-file-by-php-programming
categories: [PHP]
tags: [php, codes, snippet, excell]
---
As a PHP programmer you need to create excel file with your data by PHP programming language. I have made all the things easy. Follow just two steps and your work will be done!!


First create an Excel class in PHP with the following code
{% highlight php %}
<?php
/**
 * By Shaharia Azam
 * shaharia.azam@gmail.com
 * http://www.shahariaazam.com
 */
class Excel{

    /**
     * set the header configuration
     * @param $filename the xls file name
     */
    function setHeader($filename)
    {
        header("Pragma: public");
        header("Expires: 0");
        header("Cache-Control: must-revalidate, post-check=0, pre-check=0");
        header("Content-Type: application/force-download");
        header("Content-Type: application/octet-stream");
        header("Content-Type: application/download");;
        header("Content-Disposition: attachment;filename=$filename");
        header("Content-Transfer-Encoding: binary ");
    }

    /**
     * write the xls begin of file
     */
    function BOF() {
        echo pack("ssssss", 0x809, 0x8, 0x0, 0x10, 0x0, 0x0);
        return;
    }

    /**
     * write the xls end of file
     */
    function EOF() {
        echo pack("ss", 0x0A, 0x00);
        return;
    }

    /**
     * write a number
     * @param $Row row to write $Value (first row is 0)
     * @param $Col column to write $Value (first column is 0)
     * @param $Value number value
     */
    function writeNumber($Row, $Col, $Value) {
        echo pack("sssss", 0x203, 14, $Row, $Col, 0x0);
        echo pack("d", $Value);
        return;
    }

    /**
     * write a string label
     * @param $Row row to write $Value (first row is 0)
     * @param $Col column to write $Value (first column is 0)
     * @param $Value string value
     */
    function writeLabel($Row, $Col, $Value) {
        $L = strlen($Value);
        echo pack("ssssss", 0x204, 8 + $L, $Row, $Col, 0x0, $L);
        echo $Value;
        return;
    }
}
{% endhighlight %}

Then you will *include* this *class* file in your working PHP script with **PHP**
{% highlight php %}
require_once('pathofyourclassfile.php');
{% endhighlight %}

Then write the following code. 
{% highlight php %}
<?php
$Excel = new Excel();
// Send Header
$Excel -> setHeader('text_' . date('Y_m_d') . '.xls');
$Excel -> BOF();
/**
* Write Cell data
* writeLabel (RowNumber,ColumnNumber, "Text to put")
*/
$Excel -> writeLabel(1, 1, "Cell Value as Text");
$Excel -> EOF();
exit();
{% endhighlight %}

Now run this file and you will see one FileName.xls file will be automatically download. Open that Excel file and you will see that in your first row, first column &#8220;Cell Value as Text&#8221; will be recorded. Happy coding!