---
layout: post
title:  "Display or Print a Drupal 6/7 block anywhere"
date:   2009-08-23 13:24:59 -0700
permalink: /display-or-print-drupal-block-anywhere/
---
<p>During some development work I had to create a custom node template for a specific content type. The design had a menu block displayed on left sidebar on the majority of pages but the menu  was also needed below the content area as a secondary navigation for this content type. I searched online and what I ended up finding were a bunch of posts about creating regions with the info file or 
  putting a block in a region using the template.php.</p>
<p>These did not help because the block I wanted already existed in the left sidebar. I could've just duplicated the block but that would have been confusing to users updating the site and a waste to recreate a block that already existed.</p>
<h3>Solution</h3>
<p><code>&lt;?php<br />
$block = module_invoke('module_name', 'block', 'view', 0);<br />
print $block['content'];<br />
?&gt;</code>
</p>
<p>To use this code for any block all you need to do is changed the <code>module_name</code> and the <code>delta</code>. <strong>Note the delta of the block can be a number or a string</strong>. Something else to note is that this only prints out the block body.</p>
<div id="caption">
<img src="/img/blockinfo.gif" alt="Find module name and delta info on /admin/build/block" title="Find module name and delta info on /admin/build/block" />
<br />
Find module name and delta info on /admin/build/block
</div>
<h3>In Action</h3>
<p>Displays the user 1 block<br />
<code>&lt;?php $block = module_invoke('user', 'block', 'view', 1); print $block['content'];?&gt;</code>
</p>
<p>Prints out the primary links block<br />
<code>&lt;?php $block = module_invoke('menu', 'block', 'view', 'primary-links'); print $block['content'];?&gt;</code></p>
<h3>Resource</h3>
<ul>
	<li><a href="http://drupal.org/node/26502">http://drupal.org/node/26502</a></li>
</ul>
