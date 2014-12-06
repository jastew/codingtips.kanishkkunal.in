---
layout: post
title: Super simple Ghost Button CSS
date: 2014-11-09 03:50
author: kanishk
comments: true
categories: [CSS Buttons, Flat Web Design, Ghost Buttons, HTML &amp; CSS]
---
In this tutorial, I will show you how to create a very simple &amp; minimal Ghost Button with CSS. Ghost Buttons are quite popular these days and are trending design element while doing minimal &amp; Flat Web design.

<img class="aligncenter wp-image-19 size-full" src="http://codingtips.kanishkkunal.in/wp-content/uploads/sites/11/2014/11/simple-ghost-button-css.png" alt="simple ghost button css" width="728" height="398" />

While there are multiple ways one can approach making the Ghost button, however, I will keep it super simple and use just CSS to style our ghost button. We will also add simple hover effects to make our Ghost button give visual feedback to user when pressed.
<h2>Ghost button CSS</h2>
We will be writing a "ghost-button" CSS class (shown below) which when applied, will convert any &lt;a href=".."&gt; tag to a ghost button.

[code language="css"]
.ghost-button {
 color: #009688;
 background: #fff;
 border: 1px solid #009688;
 font-size: 17px;
 padding: 7px 12px;
 font-weight: normal;
 margin: 6px 0;
 margin-right: 12px;
 display: inline-block;
 text-decoration: none;
 font-family: 'Open Sans', sans-serif;
 min-width: 120px;
}
[/code]

The trick here is to remove the default text-decoration of links, add thin borders and define some padding to make it look like a rectangular button. On hover, we can simply fill the button with color to give visual feedback to the user.

[code language="css"]

.ghost-button:hover, .ghost-button:active {
  color:#fff;
  background:#009688;
}

[/code]

You can see the result in  codepen embed below and see the corresponding CSS and HTML files too.
<p class="codepen" data-default-tab="result" data-slug-hash="azoLpo" data-theme-id="0" data-height="268" data-user="kanishkkunal">See the Pen <a href="http://codepen.io/kanishkkunal/pen/azoLpo/">azoLpo</a> by Kanishk Kunal (<a href="http://codepen.io/kanishkkunal">@kanishkkunal</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>

If you are using RSS feed reader, or by any chance the embed above doesn't appear then please visit the <a href="http://codepen.io/kanishkkunal/pen/azoLpo/" target="_blank">Pen live on CodePen</a>

I hope that you found this CSS code snippet to make Ghost Button useful. Let me know if you have any comments or have any variations of Ghost button in mind that can be implemented with plain CSS.
