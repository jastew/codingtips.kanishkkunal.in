---
layout: post
title: Ghost Buttons on background image
categories: html-css
tags: [css-buttons, flat-web-design, ghost-buttons]
---
This is my second post in **Ghost Buttons** series. In the last one I showed how to create a simple [Ghost Button CSS]({% post_url 2014-11-09-super-simple-ghost-button-css %}) style for turning Links into Ghost Buttons. In this post we will see a better example where we will be placing the Ghost Buttons over large background images and giving it a [soft color transition effect]({% post_url 2014-11-15-color-animation-link-hover-css %}).

In Flat Web design, Ghost Buttons are generally placed over large background images or a video footage. For example take a look at <a href="http://transitions1020.com/" target="_blank">Nokia Transitions</a> website, which places a ghost button along with introduction text, over a scenic video of sea waves.

{% include image.html img="wp-content/uploads/sites/11/2014/11/ghost-buttons-background-image.jpg" title="ghost buttons background image" url="http://transitions1020.com/" %}

In this post, I will show how to make an image span the entire background and then place a ghost button over it.
<h2>Cover Background Image</h2>
For making an image span and cover the entire background of the site, we need to place it in the background property of the body tag as shown in the CSS snippet below. Note the use of  <code>no-repeat center center fixed</code> along with the background image which asks the image to be horizontally and vertically centered, not repeated over and be fixed at its position upon scroll. Also note the use of <code>background-size: cover</code> which asks the browser to scale the image as large as possible as to cover the entire viewport.

{% highlight css linenos %}

body {
     background: url(images/blurred1.jpg) no-repeat center center fixed;
     -webkit-background-size: cover;
     -moz-background-size: cover;
     -o-background-size: cover;
     background-size: cover;
}

{% endhighlight %}

<h2>Ghost Buttons on Image</h2>

We will be using the same <a title="Super simple Ghost Button CSS" href="http://codingtips.kanishkkunal.in/super-simple-ghost-button-css/">ghost button CSS</a> that we created in earlier post, with some modifications as mentioned below:
<ul>
	<li>Since we are placing the ghost button over a background image, we will make the default state color to be white (#fff)</li>
	<li>We are adding rounded edges here for button by specifying border-radius, for making the edges softer.</li>
	<li>Additionally, we will also add the soft <a title="Soft color animation on Link Hover with CSS" href="http://codingtips.kanishkkunal.in/color-animation-link-hover-css/">color transition on hover</a> that we talked about in previous post.</li>
	<li>Upon hover, the ghost button will get filled with a translucent color background.</li>
</ul>

You can find the full code along with the demo of Ghost button displayed against a blurred background image in the following code pen. As we are making use of background image, please see the result in <a href="http://codepen.io/kanishkkunal/full/dPbZBg/" target="_blank">full page view</a>.

<div class="embed">
<p class="codepen" data-height="268" data-theme-id="0" data-slug-hash="dPbZBg" data-default-tab="result" data-user="kanishkkunal">See the Pen <a href="http://codepen.io/kanishkkunal/pen/dPbZBg/">Ghost Buttons #2</a> by Kanishk Kunal (<a href="http://codepen.io/kanishkkunal">@kanishkkunal</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>
</div>

If you are using RSS feed reader, or by any chance the embed above doesn’t appear then please visit the <a href="http://codepen.io/kanishkkunal/pen/dPbZBg" target="_blank">Pen live on CodePen</a>

You will find many websites using Ghost buttons against large background images in their landing pages these days and I hope that with this tutorial you will be able to make some of your own. Do let me know if you have any feedback for the code or the way I have chosen to display or style the Ghost Buttons.
