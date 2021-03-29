---
layout: post
title:  "Custom Drupal Breadcrumb for a cck content type"
date:   2010-11-28 02:27:17 -0700
---


<p>Drupal breadcrumbs are a pain. By default they aren't the usable <a href="http://www.useit.com/alertbox/breadcrumbs.html">breadcrumb navigation</a> that people find helpful. On CCK node types they don't show any kind of site hierarchy; in fact by default they only show a link to the home page. The only place the breadcrumbs are helpful are on administrative pages. Yes, there are modules that help improve the breadcrumb system, but as a themer you can make it more usable with a few functions.</p>
<h2>Output a custom breadcrumb</h2>
<p>To do this we need to override the theme_breadcrumb function. If you don't have template.php file in your theme create one. Add to your template.php file the following function and clear your cache (change THEMENAME to the name of your actual theme).</p>
<p><code>/**<br />
  * Output a custom breadcrumb<br />
  */<br />
  function THEMENAME_breadcrumb($breadcrumb) {<br />
  // We use strip_tags instead of check_plain to prevent outputting special characters<br />
  $title = strip_tags(drupal_get_title());<br />
  if (!empty($breadcrumb)) {<br />
  return '&lt;div class=&quot;breadcrumb&quot;&gt;'. implode(' / ', $breadcrumb). ' / ' . $title .'&lt;/div&gt;';<br />
  }<br />
  // Otherwise, return an empty string.<br />
  return '';<br />
  }</code></p>
<div id="caption">
<img src="/files/default-breadcrumb.gif" alt="Custom breadcrumb using a theme override" /><br /> Shows the breadcrumb that is output using the theme override.
</div>
<p>With the theme_breadcrumb function we are customizing it to append the node title to the end of the breadcrumb. This is a good start, but to make the breadcrumb more useful we need to define a hierarchy.</p>
<h2>Generate a custom breadcrumb trail</h2>
<p>Using a custom function we build a breadcrumb trail based off the node type. I'm adding a link to a view page to the trail for the articles node type on my site.</p>
<p><code>/**<br />
  * Generate a custom breadcrumb trail<br />
  */<br />
  function THEMENAME_custom_breadcrumb($vars) {<br />
  $breadcrumb = array();<br />
  <br />
  // Set home as the first item<br />
  $breadcrumb[] = l(t('Home'), '&lt;front&gt;');<br />
  <br />
  // Add node types into breadcrumb trail<br />
  switch ($vars['node']-&gt;type) {<br />
  case 'article':<br />
  $breadcrumb[] = l(t('Articles'), 'articles');<br />
  break;<br />
  }<br />
  drupal_set_breadcrumb($breadcrumb);<br />
  return $breadcrumb;<br />
  }</code></p>
<h2>Overwrite the breadcrumb variable</h2>
<p>Now that we have our custom breadcrumb function we need to call it. Add the code below to the preprocess page function. We do a node type check because we only want to overwrite the breadcrumb with our custom function on certain node types. Otherwise if we didn't do this Drupal will simply discard it's default breadcrumb; meaning we would lose the default trail on admin pages. </p>
<p><code>function THEMENAME_preprocess_page(&amp;$vars) {<br />
if ($vars['node']-&gt;type == 'article') {<br />
$vars['breadcrumb'] = theme('breadcrumb', ishalist_custom_breadcrumb($vars));<br />
}<br />
}</code></p>
<div id="caption">
<img src="/files/custom-breadcrumb.gif" alt="Custom breadcrumb trail" /><br /> Final custom breadcrumb trail.
</div>
<h3>Resources</h3>
<ul>
<li><a href="http://api.drupal.org/api/drupal/includes--common.inc/function/drupal_set_breadcrumb/6">Drupal set breadcrumb function</a></li>
<li><a href="http://api.drupal.org/api/drupal/includes--theme.inc/function/theme_breadcrumb/6">Drupal theme breadcrumb</a></li>
</ul>
