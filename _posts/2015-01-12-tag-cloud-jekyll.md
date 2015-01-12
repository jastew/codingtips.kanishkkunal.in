---
layout: post
title: Generating Tag cloud on Jekyll blog without plugin
categories: developer-tools
tags: [jekyll]
---

[Jekyll](http://jekyllrb.com/) doesn't come with an out of box solution for generating Tag clouds, however with the support of Liquid markups and some basic CSS styling, we can generate Tag clouds ourselves without the need of any plugin. In the post I will show how I generate Tag clouds on my blogs built with Jekyll.

Jekyll is a great static site generation tool and during the past few weeks, I have moved many of my blogs including [this one to Jekyll](/github-pages-jekyll/).  I have been sharing tips on how to fill the missing pieces while making the move from [WordPress to Jekyll](/tag/jekyll/). One such missing piece is support for Tag clouds which is generally a desired element on Blogs.

Since I host a few of my Jekyll generated blogs on GitHub pages, using a plugin to generate Tag cloud is not an option for me. GitHub builds Jekyll sites with safe option which allows only a few plugins (such as sitemap) to be included in your site. Therefore I generate Tag clouds manually using Liquid markups. For e.g. see the [tag cloud on this site](/topics/) or the [tag cloud on Super Dev](http://superdevresources.com/tags/).

One distinct feature of Tag clouds is to size the tag according to the number of posts that are marked with that tag. The greater the number of posts, the bigger the size of the tag will be.  We will see how to generate such tag clouds on Jekyll shortly.

## Tags in Jekyll

Jekyll supports adding tags to a post by specifying them in the [Front Matter](http://jekyllrb.com/docs/frontmatter/). For e.g. the Front matter of this very post with tag specified as **Jekyll** is as follows.

{% highlight yaml %}
---
layout: post
title: Generating Tag cloud on Jekyll blog without plugin
categories: developer-tools
tags: jekyll
---
{% endhighlight %}

Note that, more than one tag can be specified for a Jekyll post and can be written as YAML list or a space-separated string.

You can generate Tag pages for every tag by manually creating a tag page at a path like `\tag\TAGNAME`. Posts in the tag page can be displayed by traversing the posts in `site.tags.TAGNAME` (e.g. "TAGNAME = jekyll" in this case). I will post in detail on how to create tag pages in a separate post.

## Tag cloud in Jekyll

Once you have tags setup in posts and tag pages created at URLs like `\tag\TAGNAME\`, we can create a tag cloud using the code snippet below.

{% highlight liquid %}
{% raw %}
<h1>Tag Cloud</h1>
{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="/tag/{{ tag | first | slugify }}/"
        style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{% endfor %}
{% endraw %}
{% endhighlight %}

We are traversing the tags in site after sorting them and then generating a link for every tag. While creating the link for tag page, we make sure to size every link to include the font size parameter as inline style. The size depends on the count of posts that is available for that particular site tag.

Since we are specifying the font size in percentage here, I have done offsetting by 80 after multiplying the post count by 4. By doing this, tags with just one post will be sized at 84%, those with 2 posts will have size of 88% and so on... You may want to change these offset values as per your liking.

## CSS styling the tags

We can add a bit more styling to the Tag cloud. Just some basic stuff like making them inline and adding some padding.

{% highlight CSS %}
.site-tag a {
    display: inline-block;
    margin-right: 12px;
}
{% endhighlight %}

You may want to go ahead and add more styling which matches your blog layout.

## Demo of Tag Cloud 

Find below the demo of Tag cloud that gets generated using the code snippet presented above. Note that the tags below are functional and will take you to their respective tag pages.

### Tag Cloud


<style>
span.site-tag a {
    display: inline-block;
    margin-right: 12px;
}
</style>
<div class="embed">
{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="/tag/{{ tag | first | slugify }}/"
        style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{% endfor %}
</div>

## Summary

We saw, how we can easily generate Tag clouds for Jekyll based blogs, and we don't need to resort to plugins for this purpose. By doing so, we can have these tag clouds show up on Jekyll blogs deployed with [GitHub pages](https://pages.github.com/) too. In case you have any questions or concerns, don't forget to ask them in comments below.