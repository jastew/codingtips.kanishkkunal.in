---
layout: post
title: Change color of inline SVG with CSS
description: While working on optimizing my websites for speed I decided to make use of inline SVG images instead of font icons such as Font Awesome.
categories: html-css
tags: [font-icon, svg]
---

{% include image.html img="wp-content/uploads/sites/11/2014/11/inline-svg-color.png" title="inline svg color"%}

While working on optimizing my websites for speed and in order to prepare the next version of my "<a href="http://themes.kanishkkunal.in/fastr/" target="_blank">Fastr</a>" theme for WordPress, I decided to make use of inline SVG images instead of font icons such as Font Awesome.

Font icons such as Font Awesome are great and they provide a huge amount of ready to use and scalable shapes which can be used easily on a webpage, however having so many shapes has a downside on size and therefore the speed of the site. While there exits tools like <a href="https://icomoon.io/app" target="_blank">icomoon app</a>, which can create a custom set from these font icons, I decided to go with the inline SVG approach as I find it to be more flexible in long run.

<h2>Generating SVG from font icons</h2>

If you are wondering how to generate these SVG to be used inline from a font icon, then let me tell you that it is quite easy to do with <a href="https://icomoon.io/app" target="_blank">icomoon app</a>. You can simply select the icon you want to be converted into SVG using the icomoon app, and hit on Generate SVG at bottom.
<h2>Inline SVG color</h2>
When you use an inline SVG, instead of font icon, you may have the need of changing the color of these shapes so as to match the text. In order to be able to have the colors modifiable through CSS, we are going to use shapes defined with just path. Once we have that, we can simply use the CSS property "fill" to change their color as shown in code below.

{% highlight css linenos %}

svg {
    fill: #27ae60;
}

{% endhighlight %}

You can find the complete demo in the following codepen embed. The SVG icons I used here are generated from Font Awesome icons and are in use on my site <a href="http://superdevresources.com/" target="_blank">Super Dev Resources</a>.

<div class="embed">
<p class="codepen" data-height="268" data-theme-id="0" data-slug-hash="LEPJda" data-default-tab="result" data-user="kanishkkunal">See the Pen <a href="http://codepen.io/kanishkkunal/pen/LEPJda/">SVG shapes with fill using CSS</a> by Kanishk Kunal (<a href="http://codepen.io/kanishkkunal">@kanishkkunal</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>
</div>

If you are using RSS feed reader, or by any chance the embed above doesn’t appear then please visit the <a href="http://codepen.io/kanishkkunal/pen/LEPJda" target="_blank">Pen live on CodePen</a>

<h2>Inline SVG vs Icon Fonts</h2>

Before I end this post, I would like to point you to the following two articles which will help you decide between inline SVG and Icon fonts for your own projects.

<a href="http://css-tricks.com/icon-fonts-vs-svg/" target="_blank">Inline SVG vs Icon Fonts</a>

<a href="http://mir.aculo.us/2014/10/31/icon-fonts-vs-inline-svg/" target="_blank">Why and how I ditched icon fonts in favor of inline SVG</a>
