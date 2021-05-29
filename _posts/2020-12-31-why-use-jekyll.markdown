---
layout: post
title:  "Why use Jekyll for your website?"
date:   2020-12-31 13:14:24 -0400
---

You can create simple blogs, for example this post lives in the `_posts` directory. I can edit the the post, re-build the site the changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll does have some quirks like it requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

However, you can be clever and <a href="/using-permalinks-jekyll/">refine the Jekyll permalink</a> for a friendly URL structure for SEO or to reduce the need for 301 redirects


Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Reducing maintance and comment moderation or consistent updates from content management systems like like Drupal and WordPress. It's simple Markdown, Liquid, HTML & CSS go in. Static sites come out ready for deployment. Create blogs with featurees like Permalinks, categories, pages, posts, and custom layouts are all first-class citizens here.
Intergrations with Github and Digital ocean

Avoid dealing with complex or annoying hosting companies. GitHub Pages are powered by Jekyll, so you can easily deploy your site using GitHub for free—custom domain name and all.
