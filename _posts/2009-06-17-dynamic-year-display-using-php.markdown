---
layout: post
title:  "Dynamic Year Display Using PHP"
date:   2009-06-17 13:14:24 -0400
permalink: /dynamic-year-display-using-php/
---
 
Updating things like a footer or copyright statement seem trivial, but if you have a Dreamweaver site, this could mean updating hundreds or thousands of files.
If you created the site correctly, all you have to do is edit one library file to update the text.

<p>However, you will still have to FTP the files and ensure nothing gets overwritten in the process. Or worse, if you failed to use templates and library files, you will have to manually edit those pages; <em>not cool</em>.</p>

<p>A better and long term solution would be to have the date dynamically created, that way you never have to worry about this update, ever. Besides saving you time and possibly headaches, it's also a good idea to use this approach because it shows a high level of professionalism and shows clients that you have the future of 
their site in mind.</p>
<p><img src="/img/dw-library.gif" alt="Dreamweaver Library Item" title="Dreamweaver Library Item"  /><br><em>Example of a Dreamweaver Library Item</em></p>


<p>One simple way to do this is using PHP. This code displays a copyright symbol and the current year: </p>

{% highlight ruby %}
&copy; <?php echo date('Y') ;>
{% endhighlight %}

<p>This idea can be used with other programming languages, for example JavaScript. </p>
<p>On Drupal sites, you can add this code to a <strong>footer block</strong> or to the <strong>page.tpl.php</strong>. Adding the code to <code>/admin/settings/site-information</code> will not work because PHP isn't allowed.</p>







