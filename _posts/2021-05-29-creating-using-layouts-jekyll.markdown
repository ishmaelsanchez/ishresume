---
layout: post
title: Creating layouts and using them on jekyll
permalink: /creating-using-layouts-jekyll/
date: 2021-05-29 7:49:19 -0700
---
<p>If you want a piece of content to use a different layout you can define it in the </p>
layout: home

Any file that contains a YAML front matter block will be processed by Jekyll as a special file. The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines. Here is a basic example:
{% highlight ruby %}
---
layout: post
title: Blogging Like a Hacker
---
{% endhighlight %}
Between these triple-dashed lines, you can set predefined variables (see below for a reference) or even create custom ones of your own. These variables will then be available for you to access using Liquid tags both further down in the file and also in any layouts or includes that the page or post in question relies on.

