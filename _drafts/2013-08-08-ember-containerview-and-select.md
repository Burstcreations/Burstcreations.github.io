---
layout: post
title: Ember.js ContainerView and Select working together
categories: ember views patterns
---

I'd say this is a pretty common pattern, but you can judge. Let's say we 
have a `select` input with values specifying different types of forms to fill out. We have to use a select because there is a plethora of forms, so links or tabs don't make sense. Now when an option is selected, we want to display the form below the select input.

How do we do this in Ember?

At first I wanted to resort to [computed properties][1] and handlebars [if][2] blocks, but then I realized it wasn't very scalable..

While I'm not sure if the following way is the best, or the 'Ember way', but it works nicely.

First we have to setup the select:

{% highlight javascript linenos %}
App = Ember.Application.create({});

App.IndexRoute = Ember.Route.extend({
  model: function(){
      return [
        {id: 0, value: 'Form 1' },
        {id: 1, value: 'Form 2' },
        {id: 2, value: 'Form 3' }
      ];
  }
});
{% endhighlight %}

{% gist 6188148 ContainerViewExample.js %}

See the [gist][3] or [jsbin][4] for the full code.

[1]: http://emberjs.com/guides/object-model/computed-properties/
[2]: http://emberjs.com/guides/templates/conditionals/
[3]: https://gist.github.com/knownasilya/6190792
[4]: http://jsbin.com/ekagox/1/edit