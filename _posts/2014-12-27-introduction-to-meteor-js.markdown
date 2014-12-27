---
layout: post
title:  "Introduction to Meteor JS"
date:   2014-12-27 21:26:52
categories: Web Development
author: Hassanin Ahmed
---

[Meteor](http://www.meteor.com) or Meteor JS is a complete open source platform for building web and mobile apps in pure JavaScript. It's often compared to front-end frameworks like Angular, Ember and Backbone but it is in no shape or way a fair comparison.

The Meteor stack composes of Node JS on the server and Mongo DB. It uses [handlebars](http://handlebarsjs.com) for it's front end templating. Getting started with it is incredibly easy. You won't have to worry about setting up environments for hours. I first heard about Meteor shortly after it's initial release somewhere in 2012 on [HN](http://news.ycombinator.com). It has come an incredibly long way since. Back in October of this year, Meteor finally hit version 1.0.

There is an incredible potential for Meteor not only as a Javascript framework but also as a possible managed platform like [Heroku](http://heroku.com). In mid 2012, Andreessen Horowitz splashed the cash, a massive [$11.2M first round](http://venturebeat.com/2012/07/25/meteor-funding/). I'm no accountant but that's a whole lot of money.

I plan to write more on Meteor on my blog. I would like to be more involved in the community. I even started a little [Facebook page](https://www.facebook.com/groups/meteor.malaysia) to gather a bigger resource of Meteor developers here in Malaysia.

### Here is a quick start guide on Meteor.

#### 1. Installation
{% gist 452a406810226f7c999b %}

Now navigate your browser to http://localhost:3000 and we have our first Meteor app! How incredible is that. What is even more incredible than that is how much actual code it took to display all of that. The answer is "not much."

If I type `tree .` in my terminal this is what I get. That's all it took.

{% highlight bash %}
.
|-- newapp.css
|-- newapp.html
`-- newapp.js
{% endhighlight %}

There is an executable .meteor file in the directory too but we don't need to worry about that today. We will look into it in another post.

In our newapp.html there is a bunch of HTML code that looks incomplete.

{% gist 2817c82ff2f2b5a1045a %}

It's not that the code is incomplete, it is just a partial. The final rendered version it handled by Meteor. If you want to take a look at what is being generated, just view the source from your browser. There about 39 differrent scripts that are generated and added by Meteor. These are the different libraries that make up some of the functionality of the Meteor framework. Amazing.

Let's take a look at the newapp.js file.

#### 2. Exploring newapp.js
{% gist 58cb1b5b312adb2522f8 %}

The highest level of separation is the 2 if statements. Meteor isClient and isServer. This displays the flexibility of this framework. 1 file, 2 functions. Code that runs on both the client and the server.

For the rest of this tutorial, we will take a closer look on the isClient part of the app. This is where we interact with the front-end of the application. Template.hello referes directly to the template in our HTML named "hello."

The helpers method on the template allows us to call it directly inside the template. Let's add some data that we can access it from the data.

#### 3. Adding Data 
{% gist df1a1adc8d1fa5399fbc %}

#### 4. Looping the Data
{% gist ed63064d8b5785d9d3e5 %}

Now you should be able to view a list of all the users that were passed in our helper method. Just like that we've added a new helper that allows us to pass data into our template.

Meteor is huge, it's a full stack database. I will write more in depth blog posts about adding Mongo DB collections into our app to persist data next time! Also, how to use coffeescript instead of vailla JS.

