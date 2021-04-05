---
layout: post
title:  "Quick and dirty theme upgrade from Drupal 6 to 7"
date:   2011-03-31 23:34:24 -0700
permalink: /quick-and-dirty-theme-upgrade-drupal-6-7/
---
<p>Drupal 7 has been out for a bit and I have done a handful of ports of themes from 6 to 7 and rather than go through the in depth list of items to do on <a href="http://drupal.org/node/254940">Converting 6.x themes to 7.x</a> each time, for quick ports you can follow the list below.</p>
<h2>Info file</h2>
  <ul>
  	<li>Change version</li>
    <li>Add two new regions: help and highlighted</li>
    <li>Change features[] for navigation (if applicable)</li>
  </ul>
  <h2>page.tpl.php</h2>
  <ul>
  	<li>Remove from body tag up and $closure and down (rely on new core html.tpl.php)</li>
    <li>Delete $footer_message, $primary_link, $secondary_links and $search_box </li>
    <li>Remove any hard coded skip to content links and add <code>&lt;a id="main-content"&gt;&lt;/a&gt;</code></li>
    <li>Primary and secondary links are now $main_menu $secondary_menu</li>
    <li>New region highlighted (AKA mission)</li>
    <li>Change regions from print <code>$something</code> to <code>render($page['something'])</code></li>
    <li>Add $action_links (ex. add a blog post)</li>
    <li>Add $title_prefix/suffix (RDF Goodness)</li>
</ul>
  <h2>node.tpl.php</h2>
  <ul>
<li>Clean up node wrapping div (use default $classes)</li>
  <li>Add <code>&lt;?php print $attributes; ?&gt;</code> to wrapping div</li>
  <li>Add &lt;?php print $title_attributes; ?&gt; to header titles</li>
  <li>Replace $picture with $user_picture</li>
  <li>Add $display_submitted check</li>
  <li>Add &lt;?php print $content_attributes; ?&gt; for RDF goodness</li>
<li>Use render API for $content</li>
</ul>
    
  <h2>block.tpl.php</h2>
  <ul>
    <li>Clean up block wrapping div (use default $classes)</li>
    <li>Add <code>&lt;?php print $attributes; ?&gt;</code> to wrapping div</li>
    <li>Add title prefix and suffix variables</li>
    <li>Add attributes &lt;?php print $content_attributes; ?&gt; and use render API for $content</li>
  </ul>
<h2>Extras</h2>
<ul>
  <li>Make sure features[] section in your info is right (ex. primary_links vs main_menu)</li>
  <li>Screenshots will have to be remade (Width now 295px)</li>
  <li><code>clear-block</code> is now <code>clearfix</code> (Use find and replace to fix)</li>
  <li>Dump box.tpl.php if you use</li>
  <li>Possible remove block.tpl.php and rely on core if you don't have lots of customizations</li>
  <li>Possibly use new html.tpl.php</li>
</ul>
