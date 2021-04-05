---
layout: post
title: Using !important in Your CSS
permalink: /using-important-your-css/
date: 2009-04-09 18:49:19 -0700
---
<p>In Cascading Style Sheets (CSS), the default behavior is that the most specific and last-defined rule takes the priority. That is the main reason  to use CSS; you can specify one rule and it will apply (or cascade) to all instances of that element. </p> <p>This also makes it very easy to change or update the look and feel of your site since you only have to edit one file and change the rule of one  element. Take the following example:</p>
<p><code>p {color: black;}</code> <strong>/*all instances of paragraph tags will be  black */</strong></p>
<p>To change the color of all paragraphs on our site we would need to simply change this rule. However the !important attribute after a rule takes greater precedence over any rule defined before or after. It even takes greater precedence than inline styles.</p>
<p><code>p {color: blue;!important}</code> <strong>/*all instances of paragraph tags will be blue */</strong></p>
<p>So great, now we have a way in which we can define a CSS rule that will always be honored. You can just use the <code>!important</code> attribute. </p> 
<p>Yet, this approach should probably be avoided if possible. First if your CSS is proper you probably won't have to do this (Yes, there are exceptions, but this is true for the most part.) .</p><p> Also, in terms of performance, what's going on here behind the scenes is that your CSS is being processed, the browser reads it encounters an <code>!important</code> attribute and the browser goes back to apply the styles defined by <code>!important</code>. This extra process might seem futile but if you are serving up many request you will take a hit in performance. </p>
