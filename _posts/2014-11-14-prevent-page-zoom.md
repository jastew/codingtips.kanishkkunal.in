---
layout: post
title: Prevent page zoom by user in Mobile Browser
categories: html-css
tags: web-apps
featured: /wp-content/uploads/sites/11/2014/11/prevent-page-zoom-mobile.jpg
---
Many websites and web apps prevent page zoom by user in mobile browsers such as Safari on iOS. If you are wondering how this is done then you will be amazed to know that it is possible without any JavaScript. All you need is to add a simple META tag to the head section of your webpage.

{% include image.html img="wp-content/uploads/sites/11/2014/11/prevent-page-zoom-mobile.jpg" title="prevent page zoom on mobile browser" %}

Preventing user scaling in this manner allows your web-app layout to feel more native as now users can't zoom in and zoom out on double taps or by using pinch and stretch gestures.
<h2>META tag to prevent page zoom</h2>
Add the following META tag in &lt;head&gt; section of your HTML.

{% highlight html linenos %}

<meta name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

{% endhighlight %}

If you use this meta tag, it will prevent the user from scaling and will also prevent scaling due to input focus or due to device orientation changes.

The "viewport meta tag" was introduced by Mobile Safari to let web developers control the viewport's size and scale. Many other mobile browsers (Internet Explorer on Windows Phone, Chrome on Android etc.) support this tag, although it is not part of any web standard.

Mobile browsers would generally set the viewport width to 320px for your page when you set width=device-width. You can read in detail about the viewport meta tag on <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag" target="_blank">Mozilla's doc</a>.
