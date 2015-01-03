---
layout: post
title: Full Screen Background Image with CSS
categories: html-css
tags: [responsive-web-design, flat-web-design]
featured: /images/full-screen-background-image.jpg
---

Many modern web designs have started to adopt a large background image which covers the entire width and height of browser window. The website content is placed on top of this full-screen background image. The background image remains fixed at its position as user scrolls and is also responsive, therefore is suitable to be viewed on all device sizes.

{% include image.html img="images/full-screen-background-image.jpg" title="Full-Screen background image in web design" caption="Tap on image for Demo of Full Screen background Image" url="http://codepen.io/kanishkkunal/full/MYbmzN/" %}

In this post I will show, how we can easily place such full screen background images in websites using CSS3. This code example should work in all modern browsers which support CSS3 (IE9+, Chrome, Safari, Opera 10+ and Firefox 3.6+)

##CSS code for Full-Screen background image

The full screen background image is generally placed as `background` property of `html` or `body` tag. Below we have added the CSS code to the `body` tag for setting a full screen background image.

{% highlight css %}
body {
  background: url(new-york-background.jpg) no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
{% endhighlight %}

Note the use of `background-size` property which is present in CSS3 and by setting this property to `cover` we are asking the browser to use the background image to cover the entire width and height of the browser window.

We have also asked the browser to keep the background image centered and fixed at its position. Due to this, when user scrolls, the background image stays at its place. And when user resizes the browser window, or views it on device with different sizes, the background image gets automatically stretched or clipped in order to cover the entire width and height of browser window.

## Demo of Full-Screen Background Image

As you can see it is pretty easy to set an image as full screen background image and works well with responsive web design. You can view the demo as well as the full code on CodePen using one of the options below:

<p class="text-center">
<a href="http://codepen.io/kanishkkunal/full/MYbmzN/" class="ghost-button" target="_blank">Full Demo</a> <a href="http://codepen.io/kanishkkunal/pen/MYbmzN/" class="ghost-button" target="_balnk">Full Code</a>
</p>

Or Play with the CodePen embed below:

<div class="embed">
<p data-height="368" data-theme-id="0" data-slug-hash="MYbmzN" data-default-tab="result" data-user="kanishkkunal" class='codepen'>See the Pen <a href='http://codepen.io/kanishkkunal/pen/MYbmzN/'>Full Screen Background Image</a> by Kanishk Kunal (<a href='http://codepen.io/kanishkkunal'>@kanishkkunal</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>
</div>

## Support for Older browsers

While what we did was pretty short and sweet but some of you may desire that this works on older browsers too. There is no one solution that fits all browsers, however you can take a look at different techniques suggested on [CSS-Tricks](http://css-tricks.com/perfect-full-page-background-image/) some of which include use of JavaScripts too. 

##Credit for Background Image used

The background image used in the demo above has been taken from [Pixabay](http://pixabay.com/) and is licensed CC0 i.e. free for commercial use too. You can find more such [free high quality images](http://superdevresources.com/4-sources-of-free-and-unique-high-quality-images-for-your-app/) and [free images for commercial use](http://superdevresources.com/free-images-for-commercial-use/) and many other [free resources on SuperDevResources](http://superdevresources.com/tag/free-resources/).