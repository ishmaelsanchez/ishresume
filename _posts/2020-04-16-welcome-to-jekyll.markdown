---
layout: post
title:  "Welcome to Jekyll!"
date:   2020-04-16 13:14:24 -0400
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

<p>Updating things like a footer or copyright statement seem trivial, but if you have a <a href="/tags/dreamweaver">Dreamweaver</a> site, this could mean updating hundreds or thousands of files. If you created the site correctly, all you have to do is edit one library file to update the text. However, you will still have to FTP the files and ensure nothing gets overwritten in the process. Or worse, if you failed to use templates and library files, you will have to manually edit those pages; <em>not cool</em>.</p>
<p>A better and long term solution would be to have the date dynamically created, that way you never have to worry about this update, ever. Besides saving you time and possibly headaches, it's also a good idea to use this approach because it shows a high level of professionalism and shows clients that you have the future of 
their site in mind.</p>
<div id="caption"><img src="/sites/default/files/dw-library.gif" alt="Dreamweaver Library Item" title="Dreamweaver Library Item"  /><br />
Example of a Dreamweaver Library Item</div>
<p>One simple way to do this is using <a href="/tags/php">PHP</a>. This code displays a copyright symbol and the current year: <code>&amp;copy; &lt;?php echo date('Y') ;?&gt;</code> </p>
<p>This idea can be used with other programming languages, for example JavaScript. </p>
<p>On <a href="/tags/drupal">Drupal</a> sites, you can add this code to a <strong>footer block</strong> or to the <strong>page.tpl.php</strong>. Adding the code to <code>/admin/settings/site-information</code> will not work because PHP isn't allowed.</p>
<div id="caption"><img src="/sites/default/files/d-siteinfo.gif" alt="Footer Output" title="Footer Output"  /><br />Footer Output</div>
