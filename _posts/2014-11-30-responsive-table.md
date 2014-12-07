---
layout: post
title: Responsive Table with alternate color rows
categories: html-css
tags: responsive-web-design
---
In this post I will be sharing CSS code snippet for making a simple **responsive table** with alternate color rows (**zebra stripes**). I made use of these when making leader-board tables for our <a href="http://games.kunruchcreations.com/" target="_blank">HTML5 games</a>. For e.g. take a look at <a href="http://games.kunruchcreations.com/spooky_planet/leaderboard" target="_blank">Spooky Planet's leaderboard</a> table which is responsive and has alternate color rows.

[caption id="attachment_156" align="aligncenter" width="700"]<a href="http://codepen.io/kanishkkunal/pen/yyNmNm" target="_blank"><img class="wp-image-156 size-full" title="Responsive Table with alternate color rows" src="http://codingtips.kanishkkunal.in/wp-content/uploads/sites/11/2014/11/responsive-table-zebra-stripe.png" alt="responsive table with zebra stripes" width="700" height="320" /></a> Tap on image for demo on CodePen[/caption]

<h2>CSS for Responsive Table</h2>
Please note that we are making a very simple responsive table here and this CSS code snippet may not be suitable for larger tables where all the columns can't fit into smaller width. If this is the case then you should look elsewhere for other kind of table design which can break the data apart, or provide a scrollbar for small screen devices.

For this example, we are going to assume that you have a simple table with few columns (2-4) and want to fit the entire table in the screen width-wise. To do so, all we have to do is simply apply <em>width: 100%</em> to the table tag.

{% highlight css %}
/*Responsive table*/
table {
 width: 100%;
 border-collapse: collapse;
 background: #34495e;
 color: #f3f3f3;
}

td, th {
 padding: 8px;
 text-align: left;
}
{% endhighlight %}

That's it, and now our table will fit into the width of the viewport and auto resize its columns. Note that, we are not specifying any width for our columns which will let them have a size of <em>auto</em>.
<h2>CSS for alternate color rows (Zebra Stripe)</h2>
Making table have alternate color rows is quite simple with the CSS nth-of-type selector. We pick up every odd row with this selector and change its background color as shown in CSS snippet below.

{% highlight css %}
/* Zebra striping */
tr:nth-of-type(odd) {
 background: #16a085;
}

th {
 background: #2c3e50;
 font-weight: bold;
}
{% endhighlight %}

View the demo and the full code in action for the responsive table I created with alternate color rows, using one of the options below:

<a class="ghost-button" href="http://codepen.io/kanishkkunal/full/yyNmNm/" target="_blank">View Demo</a> <a class="ghost-button" href="http://codepen.io/kanishkkunal/pen/yyNmNm" target="_blank">View Full Code</a>

As you can see, creating a responsive table is not very hard when you have small number of columns in your table. But this solution may not work for larger table and you are better off looking for other solutions such as the ones proposed on <a href="http://css-tricks.com/responsive-data-tables/" target="_blank">CSS tricks</a>.
