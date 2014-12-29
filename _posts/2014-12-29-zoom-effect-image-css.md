---
layout: post
title: Zoom Effect on Image Hover with CSS
categories: html-css
featured: /images/pixabay/lions.jpg
---

There are many ways you can add a little spice to your web design projects and one of them is adding a Zoom Effect on Images when user hovers over them. In this post I will share a simple way we can add zoom effect on Image hover with CSS.

A preview of the image hover effect that we will be creating can be seen in the image below. Hover over the image with your mouse cursor to see the effect in action.

<style>
.zoom-effect-container {
    position: relative;
    width: 100%;
    height: auto;
    min-height: 360px;
    margin: 0 auto;
    overflow: hidden;
}

.image-card {
  position: absolute;
  top: 0;
  left: 0;
  overflow: hidden;
}

.image-card img {
  width: 100%;
  height: auto;
  -webkit-transition: 0.4s ease;
  transition: 0.4s ease;
}

.zoom-effect-container:hover .image-card img {
  -webkit-transform: scale(1.08);
  transform: scale(1.08);
}
</style>
<div class="demo-wrapper embed">
<div class="zoom-effect-container">
  <div class="image-card">
      <img src="http://codingtips.kanishkkunal.in/images/pixabay/lions.jpg"/>
  </div>
</div>
</div>

##HTML for images with zoom hover effect

Applying a zoom effect is easily done by applying a scale transform using CSS, however in order to ensure that when zoom happens, the images retain their original size, that is any extra height & width gets clipped, we are going to wrap our images into few containers as shown below.

{% highlight html %} 
<div class="zoom-effect-container">
  <div class="image-card">
      <img src="http://codingtips.kanishkkunal.in/images/pixabay/lions.jpg"/>
  </div>
</div>
<div class="zoom-effect-container">
  <div class="image-card">
      <img src="http://codingtips.kanishkkunal.in/images/pixabay/peacock.jpg"/>
  </div>
</div>
{% endhighlight %}

As we can see, I have wrapped the images on which I want to apply **zoom effect** into wrapper classes called `zoom-effect-container` and `image-card`.  Next we will define CSS styles for these wrapper classes as well as for the image contained in them.

##CSS for images with zoom hover effect

For the parent container class `zoom-effect-container`, we are going to define the size we want it to retain while displaying and zooming the images within it. This generally would be same as the size of images. For my case it is `640px X 360px`. We also define `overflow: hidden` for this parent container, this is crucial if you want to clip the image to its original height & width when zoom effect is applied.

{% highlight css %}
.zoom-effect-container {
    float: left;
    position: relative;
    width: 640px;
    height: 360px;
    margin: 0 auto;
    overflow: hidden;
}

.image-card {
  position: absolute;
  top: 0;
  left: 0;
}

.image-card img {
  -webkit-transition: 0.4s ease;
  transition: 0.4s ease;
}

.zoom-effect-container:hover .image-card img {
  -webkit-transform: scale(1.08);
  transform: scale(1.08);
}
{% endhighlight %}

The inner wrappaer class called `image-card` is used to absolutely position our image inside the parent container. Next we have defined a transition duration of 0.4s for the zoom animation to play.

The actual zoom effect is being applied on the CSS `:hover` selector of parent container, and we have used a scale transform which is going to zoom the image to increase its size by 8%.

##Full Demo of Zoom effect on Images

Now that everything is in place, let's see how the final demo looks like.  You can view the Final Demo by clicking the button below. Also find the entire code of this zoom effect on codepen.

<p class="text-center">
<a class="ghost-button" href="http://codepen.io/kanishkkunal/full/emdxLm/" target="_blank">View Demo</a> <a class="ghost-button" href="http://codepen.io/kanishkkunal/pen/emdxLm" target="_blank">View Full Code</a>
</p>

Please note that you are free to use the code presented here in your own projects. In case you are wondering about the Images used in the Demo of Zoom effects, they are taken from [Pixabay](http://pixabay.com/) and are licensed CC0 and are free for commercial use too. You can find more such [free to use images](http://superdevresources.com/4-sources-of-free-and-unique-high-quality-images-for-your-app/) which are [free for commercial use](http://superdevresources.com/free-images-for-commercial-use/) too.