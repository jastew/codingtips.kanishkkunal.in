---
layout: post
title: Fixed width sidebar in responsive design
categories: html-css
date: 2014-12-10 21:39
tags: responsive-web-design
---

When I was redesigning this site, I wanted to put a **fixed width sidebar** to place ads. But since I was working on to make a **responsive design** for the site, a sidebar based on grid layouts which are based on percent-width wouldn't have solved my purpose. In this post, I will share the CSS which I used to create a fixed width sidebar for this site, while keeping the entire site layout responsive and suitable for mobile views.

You can see the final demo by tapping on the preview image below. Try resizing your browser window to see the fixed width sidebar inside a responsive layout.

{% include image.html url="http://codepen.io/kanishkkunal/full/MYKmbe/" img="images/fixed-width-sidebar-layout.png" title="Layout with fixed width sidebar" caption="Tap on image for full screen demo" %}

##HTML for page layout

Find below the HTML needed to create the layout of the page. We are using a div of class `wrapper`  to wrap our content as well as sidebar. This wrapper provides a maximum width to our page layout which I have chosen to be 1160px in the CSS. You can increase this width as per your own need. This wrapper also has left and right margin set as `auto` in CSS which helps it to stay at the center of the page.

{% highlight html %}
<div class="page">
  <div class="wrapper">
    <div class="content-wrapper">
      <div class="content-inner">
        <h1>Content</h1>
        <p>&larr; Responsive Width &rarr;</p>
      </div>
    </div>
    <div class="sidebar">
      <h2>Page sidebar</h2>
      <p>&larr; Fixed Width &rarr;</p>
    </div>
  </div>
</div>
{% endhighlight %}

We would need an additional wrapper for our content called `content-wrapper` which we are going to make of width `100%` and with a float property of `left`.  This allows our sidebar to stay on top of the content wrapper instead of flowing down.

### CSS for wrappers

This is how our final CSS looks for the page and content wrapper divs. You can ignore the min-height attribute as it has been added only to give a height to the demo without placing any content.

{% highlight css %}
.page {
  margin: 20px 0
}

.wrapper {
  max-width: 1160px;
  margin: 0 auto;
  position: relative;
  padding: 0 20px;
  min-height: 600px;
}

.content-wrapper {
  float: left;
  width: 100%;
}
{% endhighlight %}

### CSS for content and sidebar

Before writing the CSS for content and sidebar, we need to determine the size of our fixed width sidebar. I have chosen a width of 320px for our sidebar. If you choose any other size then do make sure to change the appropriate values in the CSS shown below.

{% highlight css %}
.content {
  margin-right: 320px;
  clear: both;
  overflow: auto;
  background: #1abc9c;
  background: rgba(26,188,156, 0.4);
  min-height: 600px;
}

.sidebar {
  position: relative;
  width: 320px;
  margin-left: -320px;
  float: right;
  overflow: hidden;
  background: #2c3e50;
  background: rgba(44,62,80, 0.4);
  color: #eee;
  min-height: 600px;
}
{% endhighlight %}

Depending on the fixed width of our sidebar, we have applied a margin of same width to our content. Since I am placing my fixed width sidebar on the right, I have applied a right margin. We will then give a fixed width of 320px to our sidebar with a negative margin to make it appear next to our content inside our content-wrapper.

We are pretty much done for larger screens and will have the page content have a responsive width while the sidebar maintaining its fixed width for different screen sizes. However there is still some work left to optimize it for small screen devices such as smart-phones, as this fixed width sidebar can actually take up the entire width (320px) on the small screens leaving no space for the content.

## Responsive layout on mobile

For the mobile screens, I am going to hide the sidebar altogether and just stick with the main page content. This is an ideal way to display content on small screen devices and generally you should not be placing any important content in the sidebar. Here is the CSS to hide the fixed width sidebar when viewed on mobile devices. Note that I am using a media query breakpoint of 768px, below which the sidebar will get hidden. If you want to hide the sidebar for tablets too, you may opt for a bigger size for this breakpoint.

{% highlight css %}
@media only screen and (max-width: 768px) {
  .sidebar {
    display: none;
  }
  .content {
    margin-right: 0;
  }
}
{% endhighlight %}

## Demo of fixed width sidebar

We are now done with creating our fixed width sidebar in a responsive web design layout. You can view the demo as well as the full code on CodePen using one of the options below:

<p class="text-center">
<a href="http://codepen.io/kanishkkunal/full/MYKmbe/" class="ghost-button" target="_blank">Final Demo</a> <a href="http://codepen.io/kanishkkunal/pen/MYKmbe" class="ghost-button" target="_balnk">Full Code</a>
</p>

Since, I am using this code on this blog, you see the sidebar of this site too as an example of the fixed width sidebar in responsive layout. Hope you found this Tutorial useful! Let me know if anything doesn't work for you.