---
layout: post
title: Simple Share buttons for Jekyll blog
categories: html-css
tags: jekyll
---

I recently moved this blog from WordPress to [Jekyll] and created a site structure from the plain vanilla install of Jekyll. The first thing I noticed after moving my posts from WordPress was the absence of plugins for adding share buttons in blog posts and pages, so I made a simple static one of my own. 

You can read about why I made the choice of [moving from Jekyll to WordPress]({% post_url 2014-12-09-github-pages-jekyll %}) in my previous blog post. In this post I will share the code snippet I am using to create pretty little share buttons for sharing my posts on Twitter, Facebook and Google Plus.  I will also show how you can extend it to add more services like Reddit, LinkedIn, Tumblr etc.

##Share buttons in Jekyll posts

In order to add share buttons to my posts, I used the share URLs of the social networking sites such as Twitter, Facebook and Google Plus which simply use the GET parameters passed with the URL to create the share dialog.

### Step 1: Partial include file for share buttons

I created a partial HTML file in `_includes` folder called _ `share-page.html`  which I added at the end of the post or page layouts after content. Find below the contents of this file. Notice the use of [liquid tags](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers) such as {% raw %}`{{ page.title }}` and `{{ page.url }}` {% endraw %} to automatically fetch the title and URL of the  current post or page.

{% highlight html linenos %}
{% raw %}
<div class="share-page">
    Share this on &rarr; 
    <a href="https://twitter.com/intent/tweet?text={{ page.title }}&url={{ site.url }}{{ page.url }}&via={{ site.twitter_username }}&related={{ site.twitter_username }}" rel="nofollow" target="_blank" title="Share on Twitter">Twitter</a>
    <a href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank" title="Share on Facebook">Facebook</a>
    <a href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank" title="Share on Google+">Google+</a>
</div>
{% endraw %}
{% endhighlight %}

You can find these share buttons at the bottom of this post.  Just for the sake of demo, I am including them here as well. They will be functional here too.

{% include share-page.html %}

### Step 2: CSS styling the share buttons

Next I added a bit of styling with CSS. I am giving my SCSS snippet below just in case you may want to style it in similar manner.

{% highlight scss linenoes %}
.share-page {
    text-align: center;
    background: $secondary-color;
    color: $light-color;
    padding: 8px 15px;
    border-radius: 5px;
    margin: 1.5 * $spacing-unit 0;

    a {
        font-weight: 700;
        color: #fff;
        margin-left: 10px;

        &:hover {
            border-bottom: 1px dashed #fff;
        }
    }
}
{% endhighlight %}

This is how my share buttons ended up looking. Sweet and Simple!

<div class="share-page">
    {% include share-page.html %}
</div>

## Additional Share URLs

I didn't want to create a long list of share buttons so I restricted myself to just three social sharing sites, however you can add more social networks by using the same technique. I am including the share URL structure of some of the popular social sharing sites below for your reference. Replace the URL, TITLE and other values as appropriate.

###Twitter
`http://twitter.com/share?text=<TITLE>&url=<URL>&via=<TWITTER-HANDLE>&related=<TWITTER-HANDLE>`

###Facebook
`http://www.facebook.com/sharer.php?u=<URL>&p[title]=<TITLE>`

###Google Plus
`https://plus.google.com/share?url=<URL>`

###Pinterest
`http://pinterest.com/pin/create/button/?url=<URL>&description=<TITLE>`

###LinkedIn
`http://www.linkedin.com/shareArticle?mini=true&url=<URL>&title=<TITILE>&summary=<DESCRIPTION>&source=<DOMAIN>`

###Tumblr
`http://www.tumblr.com/share/link?url=<URL>&name=<TITLE>&description=<DESCRIPTION>`

###Reddit
`http://www.reddit.com/submit?url=<URL>&title=<TITLE>`

I hope these should be enough. If you need more, you can try looking up the respective social network's developer documentation to find out their share URL.

In order to display the share count we would need to add JavaScript code to fetch and append the count. But to keep things simple and avoid unnecessary bloat to the page size, I chose not to display the share count.

##More on Jekyll coming soon
As promised, I will keep sharing my experience of hosting this blog with [Jekyll] on GitHub pages, so do stay tuned. :smiley: However, if you are in a hurry to get started with your own blog, you can see the code running this blog found on [GitHub](https://github.com/kanishkkunal/codingtips.kanishkkunal.in) for reference.


[Jekyll]:http://jekyllrb.com/