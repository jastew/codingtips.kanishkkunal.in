---
layout: post
title: Ping Sitemap to Search Engines after Site update
categories: developer-tools
tags: jekyll
featured: /images/submit-sitemap-search-engines.jpg
---

Whenever you publish a new post, or make changes to your site structure which updates the [sitemap](http://www.sitemaps.org/) of your website, it is advisable that you submit the updated sitemap to the search engines like Google & Bing to tell them about the updated content. In this post, I will show how I ping my sitemap to Search Engines after update to my sites.

{% include image.html img="images/submit-sitemap-search-engines.jpg" title="Submit Sitemap to Search Engines" %}

If you are running WordPress and using plugins like [SEO by Yoast](https://wordpress.org/plugins/wordpress-seo/), then you don't need to do this as the plugin will automatically take care of pinging your sitemap to search engines (Google & Bing) after a blog post is published or sitemap is updated. However, Since I moved to [Jekyll generated static sites from WordPress](/github-pages-jekyll/), it's required to do this task manually now.

##Pinging Sitemap to Google Search Engine

Google has the highest search traffic and you would certainly won't like to miss telling Google about your updated sitemap. It is advisable that you sign-up for [Google's Webmaster tools](http://www.google.com/webmasters/tools/) to have access to richer data and control over how Google crawls your site.

Even if you have previously submitted your sitemap to Google through Google's Webmaster tools or via the ping URL, you would need to update Google everytime your sitemap changes. 

Assuming your sitemap is at location `http://example.com/sitemap.xml` use the ping url below for Google to submit your updated Sitemap.

### Ping URL for Google
{% highlight html %}

http://www.google.com/webmasters/sitemaps/ping?sitemap=http://example.com/sitemap.xml

{% endhighlight %}

All you need to do is replace `http://example.com/sitemap.xml` with URL of your own sitemap and open the ping URL in browser of your choice such as Chrome or Internet Explorer. You would receive a message from Google stating that your updated sitemap was received and they would queue it to their crawl list.

##Pinging Sitemap to Bing Search Engine

While Bing is still lagging behind Google in search traffic, it has grown to a significant number and should not be ignored if you value traffic through search. Bing also provides access to its own [Webmaster Tool](https://www.bing.com/webmaster/) which should be used to gain richer insight to your website's search traffic through Bing.

Same goes here about sitemaps, even if you have previously submitted your sitemap to Bing through Bing's Webmaster tools or via the ping URL, you would need to update Bing every time your sitemap changes.

Assuming your sitemap is at location `http://example.com/sitemap.xml` using the ping url below for Bing  will submit your updated Sitemap.

### Ping URL for Bing
{% highlight html %}

http://www.bing.com/webmaster/ping.aspx?siteMap=http://example.com/sitemap.xml

{% endhighlight %}

All you need to do is replace `http://example.com/sitemap.xml` with URL of your own sitemap and open the ping URL in browser of your choice such as Chrome or Internet Explorer. You would receive a message from Bing stating that your updated sitemap was received.

## What about pinging other search engines?

I generally only ping my sitemaps to Google and Bing. Submitting your sitemap to Bing also gets you covered for search engines like Yahoo & [DuckDuckGo](https://duckduckgo.com/). Additionally you may want to ping your sitemap to Ask.com too via the URL below:

### Ping URL for Ask.com
**Update**: Ask.com no longer support sitmap submission via the following URL and doesn't support pinging of sitemap anymore. It's advisable that you specify your sitemap in robots.txt as explained in the next section below.

{% highlight html %}
 http://submissions.ask.com/ping?sitemap=http://example.com/sitemap.xml
{% endhighlight %}

### Specify your Sitemap in robots.txt

In order to take care of specifying the location of your websites sitemap URL for other search engines, you can add it in your site's [robots.txt](http://www.robotstxt.org/robotstxt.html). Just add the following line at the end of your site's robots.txt and all those crawlers who understand it will be able to gain access to your sitemap.

{% highlight html %}
 Sitemap: http://example.com/sitemap.xml
{% endhighlight %}

##Summary

Whether you are running a blog or maintaining a website which relies on Search Traffic, it is advisable to update search engines about the changes in your site's structure so that they can begin to crawl the updated URLs as soon as possible. All major search engines provide a way to update them with your website's sitemap via a Ping URL and we saw how we can use them in this post.

There are automated ways such as using a plugin which can do this task on your behalf, however know that unnecessarily pinging your sitemap to search engines may have a negative impact and therefore it is better to keep a manual control over it. 
