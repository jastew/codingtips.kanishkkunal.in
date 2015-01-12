---
layout: post
title: Automatically compile LESS files in WebMatrix with OrangeBits
description: As Windows is my primary development machine, I use Microsoft’s WebMatrix (free tool) to do all my web development work. I have to frequently deal with CSS, JavaScript, HTML and PHP files and I find WebMatrix to be excellent IDE
categories: developer-tools
tags: [less, webmatrix]
featured: /wp-content/uploads/sites/11/2014/11/compile-less-in-webmatrix.png
---

{% include image.html img="wp-content/uploads/sites/11/2014/11/compile-less-in-webmatrix.png" title="compile less in webmatrix" %}

As Windows is my primary development machine, I use Microsoft's <a href="http://www.microsoft.com/web/webmatrix/" target="_blank">WebMatrix</a> (free tool) to do all my web development work. I have to frequently deal with CSS, JavaScript, HTML and PHP files and I find WebMatrix to be excellent IDE for doing web development on Windows machine. It comes with many ready to use site templates, installable CMS and blogging platforms such as WordPress, Joomla etc. and can be used to directly deploy your websites to Windows Azure too.

WebMatrix also supports extensions by which the functionality of WebMatrix can be extended. Once such useful extension is <a href="https://github.com/JustinBeckwith/OrangeBits" target="_blank">OrangeBits Compiler</a> by <span class="author">JustinBeckwith. </span>OrangeBits is a WebMatrix extension that can be configured to automatically compile LESS files into CSS files and then to auto-minify the produced CSS file. Not only that, OrangeBits supports automatic compilation of SaSS, Scss and CoffeeScript too. It also has an option for Optimizing images in your project for the Web.

<h3>Configuring OrangeBits to compile LESS files</h3>

Installing OrangeBits is quite easy and can be done by searching for "Orange Bits" in WebMatrix Extensions gallery from within the WebMatrix. Learn more on <a href="http://extensions.webmatrix.com/documentation" target="_blank">how to install WebMatrix Extension</a>.

Once the installation is done, you can right click on any file in your project to view OrangeBits options in the context menu. Depending on the file you have chosen, these options will change. For e.g. on a LESS file you will find an option to <strong>compile</strong>, while on an image you will find option to <strong>Optimize</strong>. To set up the auto compilation, select the <strong>OrangeBits Option </strong>from the context menu and configure as needed. Below you can find the configuration options I selected for my setup to auto compile LESS files and auto minify CSS files.

{% include image.html img="wp-content/uploads/sites/11/2014/11/compile-less-webmatrix-orangebits.png" title="compile less files webmatrix orangebits" caption="Orange Bits Options" %}

Once configured, OrangeBits will automatically monitor changes to your files and compile them as needed.
