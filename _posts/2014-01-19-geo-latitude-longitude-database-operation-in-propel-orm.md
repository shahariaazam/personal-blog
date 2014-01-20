---
title: Geo latitude-longitude operation in Propel ORM
layout: single_post
ogDescription: Learn how to perform task for Geometric latitude, longitude in Propel ORM by using it's custom behavior. It will make so much easy to perform database operation related to latitude, longitude.
categories: [Propel]
---

{% highlight json %}
{
    "require": {
        "php": ">=5.3.0",
        "propel/propel1": "1.*",
        "willdurand/propel-geocodable-behavior": "dev-master"
    },
    "autoload": {
        "psr-0": {
            "": "src/"
        }
    }
}
{% endhighlight %}

By adding `"willdurand/propel-geocodable-behavior": "dev-master"` in **composer.json** you can use this custom **GeoCodable Behavior**. Or you can download **GeocodableBehavior.php** from [GitHub repo for this behavior](https://github.com/geocoder-php/GeocodableBehavior/tree/master/src). and put it in **/src** directory or somewhere, then register this class in your application autoloader. If you want to perform all this task by composer then just run composer update and everything will be ready for you to use.

After that, now we will go for propel's `schema.xml` file where all the database definitions are mentioned. Here, we will add the following xml node in the before **</table>** (which table will hold latitude and longitude).
`<behavior name="geocodable" />` now run the **propel-gen** command to update propel's classmap and then update your main database table structure cause it will add two column (latitude, longitude) automatically when you will update your database table structure.

Now you are ready to use the power of this `GeoCodable` behavior's power.

Basically, the behavior will add:

* two new columns to your model (`latitude` and `longitude`);
* four new methods to the _ActiveRecord_ API (`getDistanceTo()`, `isGeocoded()`,
`getCoordinates()`, and `setCoordinates()`);
* two new methods to the _ActiveQuery_ API (`filterByDistanceFrom()`,
`filterNear()`).


### ActiveRecord API ###

`getDistanceTo()` returns the distance between the current object and a given one.
The method takes two arguments:

* a geocoded object;
* a measure unit (`KILOMETERS_UNIT`, `MILES_UNIT`, or `NAUTICAL_MILES_UNIT`
defined in the `Peer` class of the geocoded model).

`isGeocoded()` returns a boolean value whether the object has been geocoded,
or not.

`getCoordinates()`, `setCoordinates()` allows to quickly set/get latitude,
and longitude values.


### ActiveQuery API ###

`filterByDistanceFrom()` takes five arguments:

* a latitude value;
* a longitude value;
* a distance value;
* a measure unit (`KILOMETERS_UNIT`, `MILES_UNIT`, or `NAUTICAL_MILES_UNIT`
defined in the `Peer` class of the geocoded model);
* a comparison sign (`Criteria::LESS_THAN` is the default value).

It will add a filter by distance on your current query and returns itself for
fluid interface.

`filterNear` takes three arguments:

* a model object;
* a distance value;
* a measure unit (`KILOMETERS_UNIT`, `MILES_UNIT`, or `NAUTICAL_MILES_UNIT`
defined in the `Peer` class of the geocoded model).

[Read more details](https://github.com/geocoder-php/GeocodableBehavior) about this Propel custom behavior class.
