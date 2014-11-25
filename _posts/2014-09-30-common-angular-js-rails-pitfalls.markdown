---
layout: post
title:  "Common Angular JS on Rails Pitfalls"
date:   2014-09-30 21:26:52
categories: Web Development
author: Hassanin Ahmed 
---

When it comes to frontend javascript frameworks, I have no secrets. My favorite one of them all is [Angular.js](http://angularjs.org).

It's amazing out of the box, it takes hardly any time to set up and it's as expressive as any framework needs to be.

When I first started learning Angular.js, I faced a stumbling block pretty quickly, I had no idea how to set it up on a Rails project. I knew how to Google but that still didn't help. I asked around a lot of bloggers but nobody put in a tutorial that was truly end-to-end. I'm not going to either, there are a lot of good ones out there today.

I want to share the 2 pitfalls that I commonly fell into when I was trying to get my Angular groove on. It's learning process.

### 1. File structure

{% highlight javascript %}
app/
  - assets/
    - javascript/
      - angular-app/ 
        - app.js
        - controllers/
        - directives/
        - models/ 
  - public
    - templates/
{% endhighlight %}

Everything angular goes into the angular-app folder and it is instantiated by the app.js file. Loading order is insanely important in Angular. Your app basically won't run if it's loaded in the incorrect order.

Templates go into the public folder. I like to create a templates folder. You can name it anything you're comfortable with.

### 2.  Minification with Rails 4

This one is interesting. You won't have to think about this until you deploy into a production environment like Heroku. Rails tries to minify the js file and the namespace loses it's meaning and Angular has no idea what you want to load. Bummer.

However, overcoming this is simple enough.

You'll need to change the minification strategy in production.rb by changing it to: 

{% highlight javascript %}
config.assets.js_compressor = Uglifier.new(mangle: false)
{% endhighlight %}

You'll also need to make sure all your angular modules are minification safe. 

A common module will look something like this

{% highlight javascript %}
angular
  .module('app')
  .factory('Claim', function($resource){
    var Claim = $resource('/api/v1/claims/:id.json', { id: '@id' }, {
      update: {
        method: 'PUT'
      }
    });
    return Claim;
  });
{% endhighlight %}

A minification safe module will require you to parse the params as an array like this

{% highlight javascript %}
angular
  .module('app')
  .factory('Claim',['$resource', function($resource){
    var Claim = $resource('/api/v1/claims/:id.json', { id: '@id' }, {
      update: {
        method: 'PUT'
      }
    });
    return Claim;
  }]);
{% endhighlight %}

These 2 issues were a big bother trying to overcome the first time I was trying to run an application with Angular. 
