---
layout: post
title: Fixing SSL_connect error while installing Ruby Gems on Windows
categories: developer-tools
tags: jekyll
---

As Windows is my primary development machine, I did a setup of [Jekyll](http://jekyllrb.com/) by following this [guide](http://jekyll-windows.juthilo.com/) by Julian Thilo. However, I ran into SSL_connect issues while installing the Jekyll gem.  

After some research, I found out that this is an issue in Ruby and I would need to manually specify an SSL certificate file. In this post I will share the specific steps I took to resolve this SSL_connect error on my Windows machine.

##Ruby SSL_connect error on Windows

After installing Ruby and Ruby Dev Kit on my machine, I ran the command `gem install jekyll`, however on first try it produced the following error:

{% highlight bash %}

> gem install jekyll
ERROR: Could not find a valid gem 'jekyll' (>= 0), here is why: 
Unable to download data from https://rubygems.org/ 
- SSL_connect returned=1 errno=0 state=SSLv3 read
server certificate B: certificate verify failed 
(https://rubygems.org/latest_specs.4.8.gz)

{% endhighlight %}

The reason why this error occurs and how to resolve it has been explained in detail by Fletcher Nichol in [this gist](https://gist.github.com/fnichol/867550). Find below the exact steps I took to resolve this SSL certificate verification failure on Windows.

##Fixing SSL_connect error on Windows

- Download the [cacert.pem file](http://curl.haxx.se/ca/cacert.pem) and save this file to `C:\RailsInstaller\cacert.pem`
- Open System in Control Panel
- Go to Advanced System Settings
- Click on Environment Variables
- Define a new System Variable with `SSL_CERT_FILE=C:\RailsInstaller\cacert.pem` as shown in screen-shot below
- Close and reopen your command prompt for allowing the changes to take place

{% include image.html img="images/fix-ssl-connect-error-windows.png" title="SSL Certificate on Windows" caption="Specifying SSL_CERT_FILE on Windows for Ruby" %}

Now we have the SSL certificate file defined permanently in our System settings. This will allow us to install Ruby gems without anymore SSL errors. You should be able to install Jekyll as well as other Ruby gems such as Rouge, Bundle etc.  In case you find the install command to be stuck for long time try running the following command to get a more verbose output.

`gem install jekyll --debug -V`

Hope you found this post useful are will be able to setup Jekyll on your Windows machine. :smiley: