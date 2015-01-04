---
layout: post
title:  "Lowershelf in Meteor JS - Part 2"
date:   2015-01-04 21:26:52
categories: Web Development
author: Hassanin Ahmed
---

Welcome back to part 2 of rewriting my [Lowershelf](http://lowershelf.herokuapp.com) application in Meteor. If you haven't taken a look at [part 1](http://hassanin-ahmed.com/web/development/2015/01/03/lowershelf-in-meteor-js-part-1.html) I suggest you do.

In this part, we're going to expand on the template by adding a search bar and the column view for the books. We will also implement the search/filter functionality.

### 1. Template

Let's start by adding a search bar template on to our current template.

{% gist df162d73eb8f1c45a934 %}

Don't forget to add it into the body tag right after the header.

Now for the main books template. We are going to interact with our database for the first time by pulling all the records of books that we have stored into it. From the array of books that we receive, we are going to loop over it and display them in a grid.

The first part is identifying a collection that we can call on. In an ideal situation, we will have a separate file for all our collections stored separately but for this example we will add it inside our lowershelf.js file.

{% gist dfc8bca22dbc32d4ad86 %}

### 2. Database interaction

{% gist e1895efc8874197ff8ea %}

In our lowershelf.js file, we've removed some of the scaffold code. There are 2 main separations, the isClient and isServer code. For now we will only work on the client portion.

In line 1, we've added a new Mongo collection by calling it. Note that we did not add `var` before the name Books. This is intentional. These assignments are valid global assignments. This is so this Books collection is available to all other files within our application. I will not cover the merits of global variables in this post but you may want to get some further reading [here](http://stackoverflow.com/a/2613647/702436).

Mongo DB calls are pretty straightforward and they are often compared to Javascript syntax. This part of the Meteor [documentation](http://docs.meteor.com/#/basic/Mongo-Collection) is helpful in getting up to speed. For the purpose of this article, look at the find and insert functions. We will explore the rest further in future articles.

If we load up our page, we'll see that it is just empty. Let's insert some books directly into the database. From a new terminal window in the root of your application, run the following commands.

{% gist 43eca8bb29201209f842 %}

Now go back to the browser and without even refreshing the page, you'll see that our new book and author comes up. Great! Let's do this a few more times with different books so we can fill up our page. I've prepared some books for you to preload into your database. From your mongo just paste the following.

{% gist c28583d26561ee3da3c1 %}

Note: We are not parsing an array into the insert function, this is the syntax to make a multiple insert into the database.

### 3. Styling

First we will extract the book template into a template of it's own. We'll have to update the books template.

{% gist baa87e67376b27b5edf8 %}

For part 2, we're going to use an image placeholder from [Lorem Pixel](http://lorempixel.com/). Think Lorem Ipsum for images.

{% gist 34ddbd3fabca6df4afb6 %}

Lastly, we'll need to fix the height of the containers so they don't float out of place. We can use some CSS to get around this.

{% gist 854eb028ee6ce04165ec %}

### 4. Filtering

Having done so much Angular JS over the last year, I find the `ng-filter` feature is one that I use constantly and the apps are much better for it. There are limitations though, out of the box, the solution doesn't work with a server side query.

In Meteor, there are ways that we can address this. This is an implementation of how we can do filtering for the books.

{% gist 6663f7d3ce576ed76136 %}

Let's take a look at the first part. The `books` helper in the books template. This is where I chose to insert a filter into our search. Note that we are only filtering through titles instead of titles and authors. We will add more filters.

As Mongo is interacts just like Javascript, we can parse in a regular expression just like that. I've also added the `i` flag to ignore case.

We will also need to get the filter from the session. In Meteor you can call get and set on Session variables from anywhere.

In line 11, we created our first template event on the searchbar template. It is important that you notice the difference in the template name. The events are handled in a very jQuery-esque manner. The event and the selector. In this case we are using the keyup event. On each keyup, we are updating the `filter` session variable. Meteor recognizes this and automatically publishes it to our `books` helper in the books template.

Now if you launch your browser again you'll see a fully functioning filter.

This is all for part 2 of rewriting Lowershelf in Meteor. It is clear to see that Meteor is an incredible platform for creating rapid prototypes and applications that are more front-end heavy.

In the next post, we will cover routing (where we can view individual books) and inserting new books from the browser. This will also integrate with an external API to get the full details of the book from it's ISBN (International Standard Book Number).

If you have any comments or questions over this post or the one before it, please feel free to contact me through any of mediums on my [contact](http://hassanin-ahmed.com/contact-me/) page. Thanks!

The code so far is on this GitHub [repo](https://github.com/sas1ni69/lowershelf-meteor). You and also browse the app on the demo [meteor server](http://lowershelf.meteor.com/).

