---
layout: post
title:  "Lowershelf in Meteor JS - Part 1"
date:   2014-12-28 21:26:52
categories: Web Development
author: Hassanin Ahmed
---

A good friend asked me today if Meteor was as productive as Rails. It is.

In some ways, Rails and Meteor are written for completely different purposes and they both should not be compared. But this is the real world, developers are going to put frameworks up against on another, no matter the purpose. This post is not about the merits of Meteor in comparison to Rails though, it is about how you can prototype quickly with Meteor.

We are not going to build a complete prototype, but we're going to write a little version of an application I've written some time ago in Rails. [Lowershelf](http://lowershelf.herokuapp.com).

### Application Description

Lowershelf is a simple marketplace to buy and sell second hand books.

1. Users can search for books
2. Users can view books
3. Users can register
4. Users can list books
5. Users can contact other users

It's a pretty straightforward application. It is interesting because it covers a few aspects of a typical of web. Authentication, some CRUD activity, search and routing. 

In this part we are going to set up the application, create a basic layout with Bootstrap and handle authentication. Let's start.

### 1. Application Setup

{% gist 5bc6113b24be4c5192c6 %}

We've added 3 packages to our new application. Installing packages with Meteor is just that simple. You don't have to require them explicitly. Meteor will handle that part for you.

### 2. Template

Now that we have our basic template up and running, let's go ahead and add some basic template. We'll start with a static navbar. First, we'll remove some of the static code template that Meteor generates.

We'll add it into a Meteor template in the same file. We will extract it out later but for now, this will suffice.

{% gist 70b7a9913f4e4a0a86c5 %}

### 3. Authentication

Much like a Ruby gem, Meteor packages can add instant functionality into an application really quickly. When we were setting up the application, we added the package `accounts-password` which creates user authentication in an instant. It handles both registration and login.

On line 27 of lowershelf.html, we've added the `loginButtons` template into our app. If you haven't, you can start the server on port 3000 simply by running `meteor` in your app directory. It'll install all the dependencies, start mongo and load up your application on port 3000.

The meteor command also gives you livereload. You are sometimes expected to restart the server when developing with Node.js. Meteor handles that for you.

Now we have really basic application with a header that allows users to sign in and login. In the final part of this tutorial, we will add authentication with Twitter and Facebook. It sounds like a big undertaking, but with Meteor, it's a breeze.

In the next part, we will cover listing books and searching/filtering.

