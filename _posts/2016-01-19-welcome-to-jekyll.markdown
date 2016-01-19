---
layout: post
title:  "Null or empty value with ng-options"
date:   2016-01-19 16:01:12
categories: javascript angular
---

{% highlight html %}
<select ng-options="item as item.label for item in items" ng-model="selected"></select>
{% endhighlight %}

In this code, the $scope.selected variable will be affected with a reference to the item selected by the user.
What if we want to allow the user to select none of the options ? Simple :

{% highlight html %}
<select ng-options="item as item.label for item in items" ng-model="selected">
  <option value="">No value</option>
</select>
{% endhighlight %}

Adding an `<option>` tag with an empty `value` attribute will allow the user to select a null value.

You can check that in the [ngOptions documentation][ngOptions].

[ngOptions]: https://docs.angularjs.org/api/ng/directive/ngOptions
