---
layout: post
title:  "Drupal 6/7 and WYSIWYG Integration"
date:   2009-12-17 23:39:36 -0700
permalink: /drupal-and-wysiwyg-integration/
---
<p>What you see is what you get (aka: WYSIWYG) editors are a necessary evil when creating Drupal sites. These client side editors simplify the creation of HTML so that non-developers can create content using HTML mark up. WYSIWYG editors can be found all over the web from email programs like Gmail to social networking sites like Myspace.</p> 

<p>So how is this related to your Drupal site? Eventually, you'll finish your Drupal site and you will have to train someone to edit and create new content on the site. Most users probably won't be comfortable creating HTML from scratch. Setting up a WYSIWYG editor can minimize the barriers to entry for new Drupal users. Below are steps I take to set up a WYSIWYG editor in Drupal 6.</p>
<ol>
	<li>Download and install the WYSIWYG module, <a href="http://drupal.org/project/wysiwyg">http://drupal.org/project/wysiwyg</a></li>
  <li>Create a &quot;libraries&quot; directory in your sites/all folder</li>
  <li>Visit /admin/settings/wysiwyg and download an editor (I use <a href="http://tinymce.moxiecode.com/download.php">TinyMCE</a>)</li>
  <li>Unpackage your editor and add the contents to your libraries directory</li>
  <li>Refresh or revisit the WYSIWYG settings page (/admin/settings/wysiwyg)</li>
  <li>If your editor was properly installed you will see a green check mark next to the editor name</li>
  <li>Select an editor for your different input formats and save your configuration</li>
  <li>Choose the &quot;edit&quot; link under the operation column</li>
  <li>Click the &quot;Buttons and plugins&quot; and define the options available for the profile</li>
  <li>Under &quot;Cleanup and output&quot; I usually check off &quot;Force cleanup on standard paste&quot;</li>
  <li>In the &quot;CSS&quot; section I remove some of the block formats and set &quot;Editor CSS&quot; to define CSS</li>
  <li>Define reusable styles in the CSS classes text area (Things like floating images, borders, text styles, etc)</li>
</ol>
<div id="caption">
<img src="/img/tinymce.gif" alt="TinyMCE" title="TinyMCE"><br />
What you should see if everything was configured properly
</div>
<p><strong>Configuration gotchas:</strong></p>
<ul>
	<li>Make sure you select the correct input format</li>
  <li>If you have troubles with content disappearing check your input format (try the HTML filter)</li>
  <li>Image upload is not native (use file attachments)</li>
</ul>
