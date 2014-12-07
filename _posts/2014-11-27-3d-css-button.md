---
layout: post
title: How to create a 3D CSS Button
categories: html-css
tags: css-buttons
---
[caption id="attachment_127" align="aligncenter" width="700"]<a href="http://codepen.io/kanishkkunal/full/KwpGNa/" target="_blank"><img class="wp-image-127 size-full" title="3D CSS Buttons" src="http://codingtips.kanishkkunal.in/wp-content/uploads/sites/11/2014/11/3d-css-buttons.png" alt="3d css buttons" width="700" height="320" /></a> Click on image for full screen demo of 3D CSS Buttons[/caption]

While I love <a href="/tag/flat-web-design/">flat web design</a>, but sometimes little things like <strong>3D CSS buttons</strong> when combined with otherwise flat design do look much more appealing to the eye. The idea is to emphasize call to action with a 3D effect on these buttons.

Many flat design websites as well as apps and games (such as <a href="http://asherv.com/threes/" target="_blank">threes</a>) make use of 3D buttons in their interface. A 3D button when clicked or tapped, displays the characteristics of being pushed downwards in a 3D manner. In this post, I will show how I created such 3D buttons myself with CSS for a cross-platform hybrid app that I am working on.

<a class="ghost-button" href="http://codepen.io/kanishkkunal/full/KwpGNa/" target="_blank">View Live Demo</a>
<h2>Create 3D CSS Button</h2>
The HTML we have, simply contains the links that we want to convert into 3D buttons. We will apply a class <em>button-3d</em> to them which we will define in the CSS.

[code language="html"]

&lt;a href=&quot;#&quot; class=&quot;button-3d&quot;&gt;Push Me&lt;/a&gt;

&lt;!--Links with button-3d class applied with convert into 3D buttons--&gt;

[/code]

<h3>The CSS</h3>
In the CSS, we are going to first define the class <em>button-3d</em> which will give button the 3D look. Much like what we did for our <a title="Super simple Ghost Button CSS" href="http://codingtips.kanishkkunal.in/super-simple-ghost-button-css/">ghost buttons</a>, we will first give some amount of padding for the button and remove default text-decoration for the link. We will also define its background color and border color (a bit lighter shade than the background color). For giving the actual 3D look, we will apply a box shadow with a color of darker shade than the background color. You may notice that I have chosen <a href="http://superdevresources.com/directory/design-resources/flat-ui-colors/" target="_blank">flat ui colors</a> here.

[code language="css"]

.button-3d {
 position:relative;
 width: auto;
 color:#ecf0f1;
 text-decoration:none;
 border-radius:5px;
 border:solid 1px #f39c12;
 background:#e67e22;
 text-align:center;
 padding:16px 18px 14px;

 -webkit-transition: all 0.1s;
 -moz-transition: all 0.1s;
 transition: all 0.1s;

 -webkit-box-shadow: 0px 6px 0px #d35400;
 -moz-box-shadow: 0px 6px 0px #d35400;
 box-shadow: 0px 6px 0px #d35400;
}

[/code]

<h3>CSS for Push Button effect</h3>
Next we will define the push button effect in the CSS active selector of our <em>button-3d</em> class. You will notice that we are reducing the box shadow and moving the button down a bit by defining the <em>top</em> attribute. By doing this a push style effect is generated, where the button moves down and its shadow decreases. Also note that, when we defined our button-3d class, we added <em>transition</em> duration of <em>0.1s</em>, this allows a gradual shift (animation) of button downwards over a duration of <em>0.1s</em> instead of an abrupt shift.

[code language="css"]

.button-3d:active{
 -webkit-box-shadow: 0px 2px 0px #d35400;
 -moz-box-shadow: 0px 2px 0px #d35400;
 box-shadow: 0px 2px 0px #d35400;
 position:relative;
 top:4px;
}

[/code]

In case you are creating 3D buttons of different sizes or with different box-shadow height, make sure to keep the sum of box-shadow height and <em>top</em> attribute in the active state same as the box-shadow height for normal state. For our case this was <em>6px</em>.

View the demo and the full code in action for the 3D buttons using one of the option below.

<a class="ghost-button" href="http://codepen.io/kanishkkunal/full/KwpGNa/" target="_blank">View Live Demo</a> <a class="ghost-button" href="http://codepen.io/kanishkkunal/pen/KwpGNa" target="_blank">View Full Code</a>
