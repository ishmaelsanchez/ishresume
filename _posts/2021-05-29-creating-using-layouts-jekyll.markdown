---
layout: post
title: Creating layouts and using them on Jekyll
permalink: /creating-using-layouts-jekyll/
date: 2021-05-29 7:49:19 -0700
---
<p>Jekyll helps you in creating full featured websites without all the maintanance and complexity of traditional content manage systems and their hosting requirements. It strikes a good balance of functionality, quick content creation and easy hosting. I don't want to discuss all the benefits of using Jekyll as there are many posts discussing that subject. What I want to focus on is how you can define layouts to customize your content per page or post.</p>

<h2>Creating Jekyll layouts</h2>

<p>Layouts are a defined template file that can be used by pages or posts which encompass their content. You create and store layouts in a speical directory called <em>_layouts</em> which lives in your site root. Layouts typically contain no front matter and have a special content variable which loads the file contents.</p>

<h2>Using Jekyll layouts</h2>
<p>Any file containing a YAML (YAML Ain't Markup Language) front matter block will be specially processed by Jekyll. The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines. So if you want a piece of content to use a different layout you can define it in the front matter of an individual file. For instance:</p>

{% highlight ruby %}
---
layout: home
title: Articles
---
{% endhighlight %}

