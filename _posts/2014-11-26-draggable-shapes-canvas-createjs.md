---
layout: post
title: Drawing draggable shapes on Canvas with CreateJS
date: 2014-11-26 19:47
author: kanishk
comments: true
categories: [Canvas, CreateJS, JavaScript]
---
While working for a cross platform hybrid app, I had the requirement of drawing draggable shapes on Canvas. I came across many JavaScript Canvas Libraries such as <strong><a href="http://calebevans.me/projects/jcanvas/" target="_blank">jCanvas</a>,</strong> which suited the purpose. However, I finally settled down for <strong><a href="http://www.createjs.com/#!/CreateJS" target="_blank">CreateJS</a>.</strong>

In this post, I will show how I created draggable shapes such as circle, rectangles and star on Canvas with <strong><a href="http://www.createjs.com/#!/EaselJS" target="_blank">EaselJS</a>,</strong> part of <strong>CreateJS</strong> library for drawing on Canvas.

[caption id="attachment_106" align="aligncenter" width="700"]<a href="http://codepen.io/kanishkkunal/full/YPPeoW/" target="_blank"><img class="wp-image-106 size-full" src="http://codingtips.kanishkkunal.in/wp-content/uploads/sites/11/2014/11/draggable-shapes-canvas.png" alt="draggable shapes on canvas" width="700" height="350" /></a> Tap on Image for Full Screen demo of draggable shapes on Canvas[/caption]
<h2>About CreateJS</h2>
CreateJS comes with a wide set of libraries called EaselJS (drawing on canvas), TweenJS (animating on canvas), SoundJS (playing sound with javascript) &amp; PreloadJS (preloading assets like sounds, images). Together they are capable of powering your next cross-platform hybrid app or game built on HTML5 Canvas. These libraries are designed to work completely independently.

In this post, I will just be using EaselJS for drawing shapes and making them draggable upon mouse or touch interactions.
<h2>Creating shapes on Canvas with EaselJS</h2>
In HTML, we need to define our canvas and give it a suitable id so that we can refer it in JavaScript. Also we hook onto the body onload event to initate our work. We link up the createjs library from the createjs CDN. That is all we need to put into our HTML as most of the work will be done in JavaScript.

[code language="html"]
&lt;script src=&quot;http://code.createjs.com/createjs-2013.12.12.min.js&quot;&gt;&lt;/script&gt;
&lt;body onload=&quot;init();&quot;&gt;
&lt;canvas id=&quot;canvas&quot; width=&quot;500&quot; height=&quot;500&quot;&gt;&lt;/canvas&gt;
&lt;/body&gt;
&lt;!--html file--&gt;
[/code]

<h3>Scale Canvas to full width &amp; height</h3>
The first thing that I will do in JavaScript init() method is to scale the canvas to occupy full width and height. This way we will make sure that our canvas is able to dynamically adjust to the screen size of user. This is done using the code below:

[code language="javascript"]var canvas = document.getElementsByTagName('canvas')[0];
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
//scale canvas
[/code]

Note that the above code will  ensure canvas resize to full screen only once i.e. upon load of html document in clients browser. If you need to adjust canvas upon every windows resize, you may want to hook onto onresize event to execute this piece of code.
<h3>Draw Geometrical Shapes on canvas</h3>
CreateJS allows us to easily draw geomterical shapes on canvas with desired size, fill and position. In order to do that, we need to first initialize a stage object with our canvas, then we create shape objects and ask CreateJS to draw the desired shape for this shape object. Afterwards we add these shape objects to the stage and call stage.update() which will do the actual drawing in the canvas.

Below you can see JavaScript code for creating and drawing circle shape which is then added to the stage. For code used to draw other shapes, please refer to the <a href="http://codepen.io/kanishkkunal/pen/YPPeoW" target="_blank">codepen</a> for this post.

[code language="javascript"]

function addCircle(x, y, r, fill) {
 var circle = new createjs.Shape();
 circle.graphics.beginFill(fill).drawCircle(0, 0, r);
 circle.x = x;
 circle.y = y;
 circle.name = &quot;circle&quot;;
 circle.on(&quot;pressmove&quot;, drag);
 stage.addChild(circle);
}
//drawing circle and adding to stage

[/code]

<h2>Making shapes draggable</h2>
As you will notice, I have registered drag function with the "pressmove" event with every shape. This will allow us to listen to the drag event on shapes and update the co-ordinates of our shape at the touch point. Since all the drawn objects are a Shape object, we use a single drag function shown below. I had to handle the square shape separately as the anchor point for square shapes is top-left.

[code language="javascript"]
function drag(evt) {
 // target will be the container that the event listener was added to
 if(evt.target.name == &quot;square&quot;) {
  evt.target.x = evt.stageX - SIZE;
  evt.target.y = evt.stageY - SIZE;
 }
 else {
  evt.target.x = evt.stageX;
  evt.target.y = evt.stageY;
 }

 // make sure to redraw the stage to show the change
 stage.update();
}
//handle drag of shapes

[/code]

<h2>Draggable Shapes Demo</h2>
See the Pen <a href="http://codepen.io/kanishkkunal/pen/YPPeoW/">Drawing draggable shapes on Canvas</a> by Kanishk Kunal (<a href="http://codepen.io/kanishkkunal">@kanishkkunal</a>) on <a href="http://codepen.io">CodePen</a>.
