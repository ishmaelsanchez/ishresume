---
layout: post
title:  "User Login Block, Drupal 6"
date:   2010-03-21 16:01:23 -0700
---
<p>While working on the <a href="/earthish">Earthish theme</a>, I wanted to theme the Drupal user login block. I did a quick Google search, but the results were not great. Many of the tutorials were about customizing the user form or customizing the login form on the user page. It was close, but that's not what I was looking for, I just wanted to theme just the login block. I did find some outdated examples, but the whole process was more challenging than I had expected. The steps below aim to simplify the process and help other Drupal themers.</p>

<p>First I tried getting as far as possible using CSS.</p>
<div id="caption"><img src="/img/user-login-css-only.gif" alt="Login CSS only"><br />
Login block with modified CSS</div>
<p>Next I used the <a href="http://drupal.org/project/devel">Devel module</a> to see what I could override and find out more about the login block. I ran into a problem here, the login form is visible only when you are logged out. Yet, using devel requires you to login. To address this issue I set the devel permissions to be viewed by anonymous users on my local development environment (<strong>Do not do this on a production website</strong>). So after changing the permissions and using devel you can see the general theme_form() function is called and ultimately used to create the login block. But, there is no specific theme function to override and since I don't want to override all forms (this was not what I wanted to do) I needed to register a theme function. </p>

<p>Themes register a theme function, by implementing the function <a href="http://api.drupal.org/api/function/hook_theme">hook_theme</a>. To register a theme function you need to know the form ID. <a href="http://getfirebug.com/">Using Firebug</a>, you can find id="user-login-form". The function hook_theme always returns an array that contains info about the hook. For forms, the name of the hook is the form ID. You can find out more about <a href="http://api.drupal.org/api/function/hook_theme">hook_theme</a> on <a href="http://api.drupal.org/">Drupal API</a>. So one would think that using user_login_form for our theme function would work. To add to the complexity, it does not because we are trying to theme the login block. Instead we need to use, user_login_block. Below is code that needs to be pasted into your theme template.php file.</p>
<p><code>/**<br />
 * Register user theme function<br />
 */<br />
function themename_theme(){ // No theme function defined for user login block<br />
  return array(<br />
    // Register theming function, it's user login block and not user login form<br />
    'user_login_block' => array(<br />
      'arguments' => array('form' => NULL),<br />
      // Template file, ex: user-login-block.tpl.php<br />
      'template' => 'user-login-block',<br />
    ),<br />
  );<br />
}</code></p>
<p>Now that we have our theme function we can create a preprocess function and template file (user-login-block.tpl.php). You don't necessarily need to provide a template file but I find it useful if you want to have more granular control of the display. Below is my preprocess function. With the preprocess fucntion you can add or modify variables. In the example below I'm changing the text of the login button to 'Login', instead of the default 'Log in'. Also, I'm modifying the text field size for the name and password fields. Here you can get creative and add or remove all sorts of information. You can use devel to see what variables are available to you. </p>
<p><code>function themename_preprocess_user_login_block(&$vars) {<br />
  // Modify the output<br />
  $vars['form']['submit']['#value'] = "Login";<br />
  $vars['form']['name']['#size'] = "12";<br />
  $vars['form']['pass']['#size'] = "12";<br />
  $vars['form_markup'] = drupal_render($vars['form']); // Print out in template file<br />
  }</code></p>
<p>For the template file, the sky is the the limit. You can create any markup you like and even print out elements individually, just like you would for any other template file. Remember to use the devel module to troubleshoot any problems while creating or modifying the template file.</p>
<h3>Resources</h3>
<ul>
	<li><a href="http://anthonymclin.com/code/7-miscellaneous/96-custom-user-login-block-on-drupal-6-zen-sub-themes">User Login Block Zen sub-themes</a></li>
  <li><a href="http://drupal.org/node/20283">Horizontal Login Block</a></li>
<li><a href="http://drupal.org/node/19855">Customizing the login form</a></li>
</ul>
