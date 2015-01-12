---
layout: post
title: Soft color animation on Link Hover with CSS
categories: html-css
tags: flat-web-design
featured: /wp-content/uploads/sites/11/2014/11/color-animation-link-hover.gif
---
Many a times, you would come across sites, where on hovering a Link you will find soft color animation happening to change the link color. Upon link hover the color of link will fade into another color over short duration instead of changing immediately. This kind of soft animation is much more soothing than having an instant color switch, which looks abrupt to the eye.

For example, in the website theme I made for <a href="http://superdevresources.com/" target="_blank">Super Dev Resources</a>, I made use of this soft color animation for post title's color change on Link hover.
<h2>CSS Color transition on Link hover</h2>

{% include image.html img="wp-content/uploads/sites/11/2014/11/color-animation-link-hover.gif" title="color animation link hover" %}

You don't need JavaScript to produce such effects. Simple CSS transition defined for color upon link hover, will produce this soft animation. Here is the CSS snippet I use to define them in my web projects.

{% highlight css linenos %}

a {
    color: #16a085;
    -webkit-transition: color .5s linear;
    -moz-transition: color .5s linear;
    -ms-transition: color .5s linear;
    -o-transition: color .5s linear;
    transition: color .5s linear;
}

a:hover { 
    color: #e74c3c; 
}

{% endhighlight %}

By doing this, we are telling the browser to change the link color from Green sea #16a085 to Alizarin #e74c3c, gradually (linearly) over a time of 0.5 seconds. You can play with the time value to achieve the desired effect, however I will suggest not to make it too slow.

You can see this code in action in the code pen embed below. Please note that I have made use of a separate CSS class "soft-link" to show the difference between default link hover and link hover effect with transition applied.

<div class="embed">
<p class="codepen" data-height="268" data-theme-id="0" data-slug-hash="ogNdmV" data-default-tab="result" data-user="kanishkkunal">See the Pen <a href="http://codepen.io/kanishkkunal/pen/ogNdmV/">Soft color animation on Link Hover</a> by Kanishk Kunal (<a href="http://codepen.io/kanishkkunal">@kanishkkunal</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>
</div>

Similar to applying transition effects on colors upon link hover, you can apply them on other attributes too such as background-color. If you are looking for spicing up your link hover effects even more then I recommend checking out these <a href="http://tympanus.net/codrops/2013/08/06/creative-link-effects/" target="_blank">Creative Link Effects</a> on Codrops.
