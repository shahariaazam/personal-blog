---
title: Use Google Web Fonts for WKHTMLTOPDF Tools to Convert HTML to PDF
layout: single_post
ogDescription: Solution- Learn how to use Google Web Fonts in your HTML for wkhtmltopdf tools to convert your HTML to PDF from command line tools.
categories: [Google Web Fonts, Web Development]
tags: [Google Web Fonts, wkhtmltopdf, PDF, HTMl Convert]
---

To convert HTML to PDF by `wkhtmltopdf` try to avoid `woff` font face. Use `trutype` format of the `Google Web Fonts` with `base64` encode.

Recently I tried to use a [google web font](http://www.google.com/fonts/#QuickUsePlace:quickUse/Family:Port+Lligat+Slab) from Google Web Fonts. But in browser it shows correctly but it doesn't show after converting HTML to PDF.

Then after searching lots of from web at last I found tools to [encode fonts](http://www.opinionatedgeek.com/dotnet/tools/base64encode/) to `base64` encoded format and also got CSS for `@font-face`.

The `base64` encoded string and CSS `@font-face` code snippet given below &#58;
<br />

{% highlight css %}
@font-face {
    font-family: 'Port Lligat Slab';
    font-style: normal;
    font-weight: 400;
    src: url(data:font/opentype;charset=utf-8;base64,d09GRgABAAAAAD00AA4A---[large string ommited]----3MAuAH/hbAEjQA=) format("woff"),
    url(data:font/truetype;charset=utf-8;base64,AAEAAAARAQAABAAQRFNJRwAAAAEAAJUIAAA---[large string ommited]-----wAAAAAAAAAAAAEAAAAA) format("truetype");
}
{% endhighlight %}
<br />

I used http://www.opinionatedgeek.com/dotnet/tools/base64encode/ to encode the font file. But remember you need encoded string for both `woff` and `truetype (ttf)`.
So now your document will be easily converted to PDF by `wkhtmltopdf` tools.