---
layout: post
title:  "Moving from Wordpress to Jekyll"
date:   2013-12-25 21:26:52
categories: Web Development
author: Hassanin Ahmed 
---

I love wordpress. I really do, but it sometimes can feel a little bloated for a simple blog. So I've decided to give a static page generator a try.

There are a lot of librarys that can do what I want to do, a simple static site that I can host on <a href="http://pages.github.com">Github Pages</a>.

I won't <a href="https://iwantmyname.com/blog/2011/02/list-static-website-generators.html">list</a> all of them but the 2 most popular Ruby options are <a href="http://www.jekyllrb.com">Jekyll</a> or <a href="http://www.octopress.com">Octopress</a>. I picked Jekyll because it seemed more popular on Github, nothing scientific about the process.

<b>Starting with Jekyll</b>

Starting with Jekyll is really simple. These are the instructions off the site.

{% highlight ruby %}
~ $ gem install jekyll
~ $ jekyll new blog
~ $ cd blog
~/blog $ jekyll serve
# => Now browse to http://localhost:4000
{% endhighlight %}

It generates a few directories inside of your blog.

{% highlight ruby %}
blog
	_layouts
	_posts
	_site
	css
	index.html
{% endhighlight %}

Anything you see on localhost:4000 is served exclusively from the _site directory. This can cause confusion when you try changing files in other directories but nothing seems to change. 

Jekyll converts all your pages which include layouts, posts and static pages to complete HTML pages. You can regenerate your site by using the build command in the terminal

{% highlight ruby %}
~ $ jekyll build
{% endhighlight %}

Be careful though, any changes you've made to the _site directory will be overriden.

In the next few posts, I will write about changing your template, writing posts with markdown, deploying on Github and adding a custom domain. See you soon and happy Christmas!