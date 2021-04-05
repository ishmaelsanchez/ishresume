---
layout: post
title: Redirect authenticated Drupal users 
description: Redirect authenticated users to overview page instead of homepage in Drupal 6 and 7
permalink: /redirect-authenticated-drupal-users/
date: 2010-10-28 16:46:51 -0700
---
<p>So I was recently working on a project and there was a requirement to have anonymous users view a simple homepage with a sign up form.
This is easy enough, create a page (/node/add/page) and add the sign up form (See below, quick and dirty), and set the default front page to this newly created node on /admin/settings/site-information.</p>
<p>Prints out the Drupal registration form usually found on /user/register <br />
<code>&lt;?php<br />
  include_once(drupal_get_path('module', 'user') .'/user.module');<br />
print drupal_get_form('user_register')<br />
</code><code>?&gt;</code></p>
<p>So this works great, but when an authenticated users visit the homepage they will see the registration form which is somewhat confusing. To make things more user friendly we can redirect them to an overview page. We can do this with a simple custom module. Once you have your module folder and basic .info file set up add the following code to your .module file.</p>
<p>/**<br />
  * Redirect authenticated users to overview page instead of homepage<br />
  */
  <br />
  function MYMODULE_init() {
global $user;
 if ($_GET['q'] == 'node/10' and $_SERVER['SCRIPT_NAME'] == '/index.php' and $user->uid) drupal_goto('overview');</p>
<p>Just replace the node id with the id of your actual front page node (see /admin/settings/site-information) and just make sure you have a page with the path overview or some other custom page.</p>
<h3>Resources</h3>
<ul>
 <li><a href="http://groups.drupal.org/node/15764">How to have two front pages</a></li>
</ul>
