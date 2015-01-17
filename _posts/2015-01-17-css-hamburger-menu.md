---
layout: post
title: Creating a CSS only Hamburger Menu Icon (no Images or Icon Fonts)
categories: html-css
tags: [responsive-web-design, flat-web-design]
featured: /images/css-hamburger-menu-icon.png
---

In this post, I will be sharing CSS code snippet for creating a hamburger menu without any Images or Icon Fonts. Hamburger menu are often used in responsive web design to depict an expandable list of menu. It is possible to create this three line menu icon with only CSS, and we will see how in this post.

{% include image.html img="images/css-hamburger-menu-icon.png" title="CSS only Hamburger menu" url="http://codepen.io/kanishkkunal/pen/QwvWwr" caption="Tap on Image for demo on CodePen" %}


## Why use CSS only Hamburger menu icon

When designing minimal websites, you may not desire to load unnecessary Icon Fonts such as [Font Awesome](http://fortawesome.github.io/Font-Awesome/) or extra images just to create one small hamburger menu icon. It is best to use a CSS only Hamburger menu icon is such cases to avoid extra resource request calls for the website.

The CSS, we will be writing for creating our Hamburger menu icon will be supported by many old browsers too and therefore it's a better option than to use SVG or Icon Fonts which are generally not supported by older browsers and require additional fallback methods.

## Pure CSS Hamburger Menu Icon

If you are wondering, how is it possible to draw three lines in same element with CSS, then the answer to that is pseudo elements. As seen in the CSS snippet below, we are drawing top and bottom border to the `hamburger` element. For the third line which will draw in between, we are using the `:before` pseudo class using which, we are able to absolute position our third line in between the first two.

### CSS
{% highlight css %}
.hamburger {
    position: relative;
    display: inline-block;
    width: 1.25em;
    height: 0.8em;
    margin-right: 0.3em;
    border-top: 0.2em solid #fff;
    border-bottom: 0.2em solid #fff;
}

.hamburger:before {
    content: "";
    position: absolute;
    top: 0.3em;
    left: 0px;
    width: 100%;
    border-top: 0.2em solid #fff;
}
{% endhighlight %}

As you can see, I used `em` instead of `px` so the menu drawn will be scalable relative to the font size. Once we have this CSS in place, using the HTML snippet below, we can create our hamburger menu.

### HTML

{% highlight html %}
<span class="hamburger"></span> Menu
{% endhighlight %}

### Demo

Find the [full code and demo](http://codepen.io/kanishkkunal/pen/QwvWwr) on my pen at CodePen. In case you are interested in seeing this kind of hamburger icon in action, then head over to [Super Dev](http://superdevresources.com/) from mobile browser, or resize the browser window to see the main navigation menu turn into hamburger menu with icon made with CSS.

##Bonus CSS icons

{% include image.html img="images/pure-css-icons.png" url="http://saeedalipoor.github.io/icono/" title="Icono - pure css icons" %}

If you need to draw more icons with just CSS, then I came across this [github project](http://saeedalipoor.github.io/icono/) which has many more Pure CSS icons.
