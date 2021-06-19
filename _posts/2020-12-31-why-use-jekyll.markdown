---
layout: post
title:  "Why use Jekyll for your website?"
date:   2020-12-31 13:14:24 -0400
---
As a web developer (or not) building websites is easy. The thing is once you create a website that's just the start of the project NOT the end. The technology you choose to build your website should be based on a variety of diffrent factors. One important consideration should always be trying to reduce effort. The problem with websites lie in maintaining many websites. When the number of sites you manages is in the dozens or hundreds this maintenance becomes a burden. This is where using a static site generator like Jekyll can help you. 


Many devlopers use open source software like Drupal, WordPress, Joomla, TYPO3, etc. If your website is powered by one of these technologies you'll have to regularly apply updates and/or security patches. While there are solutions like Pagely's automatic updates of WordPress nothing is fool proof (i.e. updates could break custom code thus causing rework of existing functionality). Jekyll doesn't require regular codebase updates or security patches because your website is generated and output as HTML and CSS.

On top of regular patching, another common issue with websites platforms is code bloat. Using add-ons, plugins or modules while they add functionality, they often add large amounts of HTML markup, JavaScript and CSS to your website pages. This in turn increases page load and slows down the rendering of your website. While you can strip out some of this code, often it's not trivial (i.e. overriding theme functions in Drupal). Jekyll wins here again since outputs simple markup without all the hassle. 

Hosting is another common issue with websites. While most hosting is relatively inexpensive, it can be a pain to deal with the complexity from different hosting environments and regardless it's an added responsiblity. Jekyll has an advantage here in its simplicity. GitHub Pages are powered by Jekyll, so you can easily deploy your site using GitHub. Additionally, you can use a custom domain name. Also, there are intergrations with Github and hosting providers like Digital ocean.



You can create simple blogs, for example this post lives in the





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

It's simple Markdown, Liquid, HTML & CSS go in. Static sites come out ready for deployment. Create blogs with featurees like Permalinks, categories, pages, posts, and custom layouts are all first-class citizens here.



