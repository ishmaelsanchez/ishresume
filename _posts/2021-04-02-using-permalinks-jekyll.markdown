---
layout: post
title: Using permalinks in jekyll for SEO friendly URLs
permalink: /using-permalinks-jekyll/
date: 2021-04-02 18:49:19 -0700
---
<p>Jekyll makes creating your site easy and reduces the burden of constant updates from content management systems like Drupal, Wordpress and AEM. However, you don't have to sacrifice regular and easy content creation. Jekyll has blogging build it and you can write blog posts as text files along with easily creating pages. I wont cover how to write posts, pages or the basic structure since there are many posts covering those subjects. What I do want to discuss is how you can use permalinks to customize your Jekyll site URLs.</p>

<p>First, you define a permalink in the Front Matter of an individual page. This will override the default for both pages and posts. This is extremely useful when migrating from an existing content management system. For example, I had a old Drupal site where I created an article landing page at /articles. When I moved that page to Jekyll I simply defined the same /articles permalink and I was all set.</p>
  
{% highlight ruby %}
---
title: Articles
permalink: /articles/
---
{% endhighlight %}
  
<p>However, when I wanted to simplify my pages when moving from Drupal I wanted to convert some landing pages I previously had into posts although I wanted to maintain my previous SEO friendly URL. Jekyll has your back here and if you want to customize your URLs to something other than the default YEAR-MONTH-DAY-title.MARKUP you can simply define the permalink in your posts.</p>
  
{% highlight ruby %}
---
layout: post
title: Using permalinks in jekyll
permalink: /using-permalinks-jekyll/
---
{% endhighlight %}

<p>Jekyll makes it easy to customize your URL structure. You can define exactly what we want the URL to be on page or post basis based on our needs. </p>



