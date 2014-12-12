---
layout: post
title: Super simple Ghost Button CSS
categories: html-css
tags: [css-buttons, flat-web-design, ghost-buttons]
modified: 2014-12-12
---

In this tutorial, I will show you how to create a very simple &amp; minimal Ghost Button with CSS. Ghost Buttons are quite popular these days and are trending design element while doing minimal &amp; Flat Web design.

{% include image.html img="wp-content/uploads/sites/11/2014/11/simple-ghost-button-css.png" title="simple ghost button css"%}


While there are multiple ways one can approach making the Ghost button, however, I will keep it super simple and use just hand-coded CSS to style our ghost button. We will also add simple hover effects to make our Ghost button give visual feedback to user when pressed or hovered upon.

<h2>Ghost button CSS</h2>

We will be writing a "ghost-button" CSS class (shown below) which when applied, will convert any `<a href="..">` tag to a ghost button.

{% highlight css linenos %}

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

{% endhighlight %}

The trick here is to remove the default text-decoration of links, add thin borders and define some padding to make it look like a rectangular button. 

## Ghost Button hover effect
On hover, we can simply inverse the color, that is we will fill the button with the text color and text with the background color. This will give visual feedback to the user when he presses or hover upon this ghost button.

{% highlight css linenos %}

.ghost-button:hover, .ghost-button:active {
    color:#fff;
    background:#009688;
}

{% endhighlight %}

## Demo of Simple Ghost Buttons

You can see the resultant Ghost Buttons in the codepen embed below and see the corresponding CSS and HTML files too.

<div class="embed">
    <p class="codepen" data-default-tab="result" data-slug-hash="azoLpo" data-theme-id="0" data-height="268" data-user="kanishkkunal">See the Pen <a href="http://codepen.io/kanishkkunal/pen/azoLpo/">azoLpo</a> by Kanishk Kunal (<a href="http://codepen.io/kanishkkunal">@kanishkkunal</a>) on <a href="http://codepen.io">CodePen</a>.</p>
    <script src="//assets.codepen.io/assets/embed/ei.js" async=""></script>
</div>

If you are using RSS feed reader, or by any chance the embed above doesn't appear then please visit the <a href="http://codepen.io/kanishkkunal/pen/azoLpo/" target="_blank">Pen live on CodePen</a>

I hope that you found this CSS code snippet to make Ghost Button useful. Let me know if you have any comments or have any variations of Ghost button in mind that can be implemented with plain CSS.

##Next Steps

While what we have created is a good example of Ghost Buttons that you may encounter in your daily visits to some of the modern designed websites, we are not done here and can add little more effects as well as visual appeal. Learn how by reading my text tutorial [Ghost Buttons on background image]({% post_url 2014-11-18-ghost-buttons-background-image %})
