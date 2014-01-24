---
title: Add Google places address suggestion in your address field
layout: single_post
ogDescription: See a little snippet about to add address or place suggestions by Google Places in your form's text field or address field to avoid user's misspelled typing while searching address on map.
categories: [JavaScript]
---

To avoid misspelled user typing of address for searching places or anything by Google map, you can place only address suggestion dropdown provided by Google places API. It's so easy to integrate.

Just add the following Javascript code before **</head>** tag.

{% highlight js %}
<script src="https://maps.googleapis.com/maps/api/js?sensor=true&libraries=places"></script>
{% endhighlight %}

Now let's assume your input field/ address field code in your form is-

{% highlight html %}
<input type="text" class="form-control" id="locationInput" placeholder="write your address">
{% endhighlight %}

Now put the following javascript code after adding the google api javascript file source.

{% highlight js %}
<script>
  (function(){
    var options = {
                    types:  ['geocode']
                  };
    
    var input1 = document.getElementById('locationInput');
    var autocomplete = new google.maps.places.Autocomplete(input1,options);
  })();
</script>
{% endhighlight %}

Now when you will try to type something on your address field then automatically google will show possible address suggestions for you.
