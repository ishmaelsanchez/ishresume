---
layout: post
title: Using Cufon
description: Using Cufon in your Drupal theme
permalink: /using-cufon/
date: 2010-07-30 16:54:22 -0700
---
<p>Dealing with web typography can be a disaster.  Finding a font that fits the site, setting the font-family CSS property (and "<a href="http://ww.w3.org/TR/CSS2/fonts.html#generic-font-families">fallback option/s</a>"), then testing the rendering in different browsers. And even after all that you are still hoping the first font is even installed on the user's operating system and if not you just have to deal with the rendering of a generic web-safe font. A second option would be to use images, but that makes things harder to maintain and change. A third option is text replacement. There are several way to implement this Cuf&oacute;n, Google Font API, sIFR, P+C DTR, SIIR, and many more. I have used Cuf&oacute;n succesfully and wanted to share my general process and how to use it with <a href="/tags/drupal">Drupal</a>. </p>
<p>First, why use <a href="http://wiki.github.com/sorccu/cufon/about">Cuf&oacute;n</a>?</p>
<ul>
  <li><a href="http://wiki.github.com/sorccu/cufon/browser-support">Browser Support</a></li>
  <li>Easy to use </li>
  <li>Doesn't require Flash</li>
  <li>Rendered using only JavaScript (Degrades gracefully if JavaScript isn't enabled)</li>
</ul>
<p>Ok, sold. How do you use it?</p>
<ul>
  <li>Find a font (TrueType or OpenType) and download it</li>
  <li><a href="http://cufon.shoqolate.com/generate">Convert the font to be compatible with Cuf&oacute;n</a></li>
  <li><a href="http://cufon.shoqolate.com/js/cufon-yui.js">Download the Cuf&oacute;n script</a></li>
  <li>Replace text using <code><a href="http://wiki.github.com/sorccu/cufon/usage">Cufon.replace</a></code> (Not a good idea to do this for body text)</li>
</ul>
<div id="caption">
<img src="/img/cufon-files.gif" alt="Cufon Files" /><br />
Files needed to use Cuf&oacute;n
</div>
<h3>Drupal and Cuf&oacute;n</h3>
<p>Using Cuf&oacute;n in your Drupal theme</p>
<ol>
  <li>Add the Cuf&oacute;n script and the generated font file to your theme</li>
  <li>Create another script file and call <code>Cufon.replace</code></li>
  <li>Include the scripts in your info file (Make sure the path is correct and lead with the main Cufon file)</li>
  <li>Clear your cache</li>
</ol>
<div id="caption">
<img src="/img/info-file.gif" alt="Add Cufon to your Drupal theme"  /><br /> My info file, note the path all my scripts are in a js folder.
</div>
<p>There is a <a href="http://drupal.org/project/cufon">Cuf&oacute;n module</a>, but if I can accomplish something at the theme level without installing a module I will. Having said that I have never used this module so it might be worth checking out if you can't set up Cuf&oacute;n or are having difficulties.</p>
<h3>Resources</h3>
<ul>
  <li><a href="http://cufon.shoqolate.com/js/cufon-yui.js">Download Cuf&oacute;n script</a></li>
  <li><a href="http://cufon.shoqolate.com/generate">Cuf&oacute;n automated tool generator</a></li>
  <li><a href="http://wiki.github.com/sorccu/cufon">Cuf&oacute;n wiki</a></li>
  <li><a href="http://www.sooperthemes.com/drupal-blog/cufon-your-drupal-theme-4-steps">Cufon your Drupal Theme in 4 Steps</a></li>
</ul>
