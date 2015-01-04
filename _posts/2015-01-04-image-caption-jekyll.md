---
layout: post
title: Display Image caption in Posts on Jekyll blogs
categories: developer-tools
tags: [jekyll]
featured: /images/pixabay/bmw-bike.jpg
---

After moving this blog from [WordPress to Jekyll](/github-pages-jekyll/), I have been trying to manually patch all the gaps that I found between Jekyll & WordPress. One of them is the support for displaying Image captions along with the the image in posts. It is quite easy to add support of Image caption on Jekyll powered blog yourself and we will see how in this post.

{% include image.html img="images/pixabay/bmw-bike.jpg" title="BMW Bike" caption="Images with Caption" %}

Unlike WordPress, there are many things that don't come prepackaged with Jekyll. For a developer like me, it is actually a good thing as it gives me the opportunity to build it myself and make it the way I like it to be. For e.g. [Share buttons for Jekyll](/share-buttons-jekyll/). However, it can be taxing for others as basic things like adding a caption on the image in posts, which was pretty easy on WordPress, will now require you to add HTML code in your Jekyll post (along with markdown) to make it work. 

##Image Caption in Jekyll posts

To make it easier for everyone, I am sharing my working solution which will allow you to easily insert image in your posts on Jekyll and add a caption to it. Along with that, you can also specify **alt** text, add a **link (URL)** to it and specify a **title** for the link too.

### Include file image.html for Jekyll
In order to add support of Image Captions, I have created a partial include file for Jekyll named `image.html` and placed it in my `_includes` folder. The content of this file is presented below

{% highlight html %}
{% raw %}
<!-- _includes/image.html -->
<div class="image-wrapper" >
    {% if include.url %}
    <a href="{{ include.url }}" title="{{ include.title }}" target="_blank">
    {% endif %}
        <img src="{{ site.url }}/{{ include.img }}" alt="{{ include.title }}"/>
    {% if include.url %}
    </a>
    {% endif %}
    {% if include.caption %}
        <p class="image-caption">{{ include.caption }}</p>
    {% endif %}
</div>
{% endraw %}
{% endhighlight %}

Note that, I am making use of [Liquid tags](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers) to access parameters passed to this include file. The parameters that we are going to pass are as follows:

- **img:** the path to image file e.g. "/images/myimage.jpg"
- **title:** the title of the image which will be used for its alt text and as the link title (if any)
- **url:** (optional) the url the image will point to
- **caption:** (optional) the caption of the image which will be displayed below the image.

I have also added CSS classes in order to be able to style these Images with Captions. Find the CSS code used to style them below.

### CSS style for Images with Captions
In order to make our caption stand out, we are going to use the following SCSS code which will change the color of our caption text and will also make the image as well as caption text centered.

{% highlight scss %}
.image-wrapper {
    text-align: center;

    .image-caption {
        color: $grey-color;
        margin-top: $spacing-unit / 3;
    }
}
{% endhighlight %}

### Inserting images with caption in Jekyll posts

So, now that we have this include file and corresponding style defined in our CSS, here is how you can include an image with caption in your posts.

{% highlight html %}
{% raw %}
{% include image.html
            img="images/myimage.jpg"
            title="title for image"
            caption="caption for image" %}
{% endraw %}
{% endhighlight %}

### Images with caption & linked to URL too
To link the image to a URL, simply specify the `url` parameter for the include file as shown below.

{% highlight html %}
{% raw %}
{% include image.html
            img="images/myimage.jpg"
            title="title for image"
            caption="caption for image"
            url="http://example.com" %}
{% endraw %}
{% endhighlight %}

## Example of Image with Caption

I added an example at the begining of the post, here is another example of an image with caption text and a link too. Notice that `alt` text as well as `title` for the URL are also present in the image.

{% include image.html img="images/pixabay/color-pencils.jpg" title="Color Pencils" caption="Images with Caption & URL" url="http://example.com" %}

##Summary

While Markdown is great for writing posts in Jekyll, those of us moving from WordPress might find in-built support for a few things missing such as Caption on Images. However it is possible to create a partial include file for Jekyll which can be reused for inserting Images with Caption. In this post, I shared my way of adding caption to images on my blogs built with Jekyll. 

Along with caption, the include file presented here, also ensures that proper "alt" tag and "title" tag get added to your images, which will be good for Search Engine Optimization (SEO) of the images in your posts. If you found this useful, you may want to read my other posts on [Jekyll](/tag/jekyll/) too.