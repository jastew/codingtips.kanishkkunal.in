---
layout: post
title: Coding Tips now running on GitHub Pages powered by Jekyll
categories: developer-tools
tags: jekyll
featured: /images/octojekyll-opt.jpg
---

I have moved hosting of my Coding Tips blog to [GitHub Pages]. At the core, [Jekyll] is being used to generate static HTML pages for this site which is getting hosted by GitHub.

##WordPress to Jekyll

Earlier I was hosting this blog with WordPress, therefore I had to do a bit of work in moving my posts over to Jekyll. I also took this opportunity to create a cleaner theme for the site. I will soon be posting about different problems I faced and solutions I resorted to while doing this move from WordPress to Jekyll.

Until then, here is a bit of overview of what changed. WordPress runs on PHP and MySQL and generates dynamic HTML pages. This requires a server capable of running these softwares. Serving dynamic pages made with PHP, which in turn is accessing database such as MySQL, is quite heavy operation. Many solutions exist to cache and improve performance of WordPress hosted website, and I am still using it on many of my other websites. But still it takes running a decent server to power WordPress hosted websites if you want to good performance.

Serving a static page, as opposed to a dynamic page is not only faster, but also more secure. Jekyll is capable of powering a simple blog and converting it into simple static pages which can be served directly without the need of server processing involved. A static site also means, no constant hack attempts (there is no login/dashboard on this site), no need to be updating WordPress, PHP and other softwares for getting up to speed with the security requirements, no need of cache plugins and other security/performance plugins. All in all it's a peace of mind.

What's more, you can choose to host Jekyll sites on [GitHub Pages], a service by GitHub which is completely free. Even mapping with your custom domain costs nothing. Yes, you read that right, nothing, zero, zip, zilch, nada.

<div class="text-center">
{% include image.html img="images/octojekyll-opt.jpg" url="http://jekyllrb.com/" title="Jekyll" caption="Jekyll's Octocat mascot. (Image credit: GitHub)" %}
</div>

##Ready to move to Jekyll?

If you are convinced as I was, and are ready to move your own blog to Jekyll then find a nice tutorial by Smashing Magazine below which can serve as a great starting point.

Tutorial - **[Build A Blog With Jekyll And GitHub Pages](http://www.smashingmagazine.com/2014/08/01/build-blog-jekyll-github-pages/)**

In the article mentioned above, the author mentions about [Jekyll-now](http://github.com/barryclark/jekyll-now) which is a fantastic theme as well as a good starting point to run your own blog with Jekyll on GitHub Pages. There are couple of other options also which are listed below.

### Jekyll themes
 - [Hyde](https://github.com/poole/hyde) by MDO
 - [Lanyon](https://github.com/poole/lanyon) by MDO
 - [Left](https://github.com/holman/left) by Zach Holman
 - [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) by Michael Rose
 - [Skinny Bones](https://github.com/mmistakes/skinny-bones-jekyll) by Michael Rose

### Theme used on Coding Tips

I started with [Jekyll-now](http://github.com/barryclark/jekyll-now) and found it to be good, but then I needed a two column layout so I made a template of my own. The entire code powering this site is [available on GitHub](https://github.com/kanishkkunal/codingtips.kanishkkunal.in) and is MIT licensed. You are free to fork the repo of Coding Tips and start your own blog after doing your own customizations and removing my content. :smiley: 

Do let me know how it goes. As promised earlier, I will soon be posting more articles sharing my experience in moving from WordPress to Jekyll, so stay tuned.


[GitHub pages]:https://pages.github.com/
[Jekyll]:http://jekyllrb.com/