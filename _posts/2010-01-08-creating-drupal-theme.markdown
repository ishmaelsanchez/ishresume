---
layout: post
title:  "Creating a Drupal theme"
date:   2010-01-08 16:38:04 -0700
permalink: /creating-drupal-theme/
---
<p>Sometimes an existing Drupal theme just will not do. Or possibly you might have a designer that has PSD or InDesign file of exactly how you want your site to look. At this point you could try to find an existing theme that mostly works and just tear apart the CSS and HTML and customize it until you get the look you want. Or you could create a sub-theme from a starter theme like <a href="http://drupal.org/project/zen">Zen</a> or <a href="http://drupal.org/project/genesis">Genesis</a> and start creating the refining the HTML and CSS to match your design. </p>
<p>There is nothing wrong with either of the approaches I mentioned above, and I have built sites using both methods (although for maintenance purposes sub-themes are preferred). Recently though, I want more control over my themes. So I have created a couple custom themes and thought I would share my process for doing this.</p>
<ol>
<li>Develop a design file (Or have someone do it for you)</li>
  <li>Convert the design file into pure HTML and CSS</li>
  <li>Create the theme folder, info file, and other basic assets</li>
  <li>Modify the HTML and convert into template files (page.tpl.php, node.tpl.php, block.tpl.php, etc)</li>
  <li>Customize output by overriding theme functions (template.php)</li>
  <li>Add any custom variables (template.php)</li>
  <li>Refine HTML and CSS (Don't forget about styling the admin pages)</li>
</ol>
<h3>Resources</h3>
<ul>
	<li>
	 <a href="http://drupal.org/node/171194">Anatomy of a Drupal 6 theme</a>	</li>
  <li>
  <a href="http://tips.webdesign10.com/how-to-make-a-drupal-theme">How to Make a Drupal Theme</a>  </li>
</ul>
