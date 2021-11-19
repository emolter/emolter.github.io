---
title: "Making this website"
excerpt_separator: "<!--more-->"
categories:
  - Tutorials
tags:
  - website
  - jekyll
---

I here document how I made this website and what I learned. I hope this post helps someone else make their github.io site for the first time, or just reminds me in a few months what I did.  Thanks to Murti for pointing out that I can host a website on github.io this way. In order to have it at username.github.io you just need to name the repo precisely "username.github.io". Making my site here instead of at a berkeley.edu address seems like the best decision for someone who might change research positions a few times in the next few years. The repo that underlies the website is [here](https://github.com/emolter/emolter.github.io).

# Software Prerequisites

GitHub supports building websites using [Jekyll](https://jekyllrb.com/). Jekyll was easy to install with just 
{% highlight bash %}
gem install jekyll bundler
{% endhighlight %}
once I had installed the appropriate Ruby versions. Ruby was the hard part, as it seems pretty annoying to install without homebrew and the version on my Mac was 2.3 when I needed at least 2.5. I used the rbenv ruby environment handler, and had to install it by hand via [these instructions](https://github.com/rbenv/rbenv#basic-github-checkout). Once that was done, I was able to just run
{% highlight bash %}
rbenv install 2.7.4
{% endhighlight %}


<!--more-->

# Minimal Mistakes

Now I needed a Jekyll template since the default from GitHub Pages seemed a bit basic. [Minimal Mistakes](https://github.com/mmistakes) came through bigtime. I spent a long time trying to use a different free Jekyll template, but its homepage was kind of dumb-looking and I couldn't figure out easily how to change it. The fact that Minimal Mistakes had a [quickstart](https://github.com/mmistakes/mm-github-pages-starter/generate) that made the GitHub repo for me was pretty awesome.  And it looks easy to change any layouts or settings by simply adding more files from the main Minimal Mistakes repo into my local repo for the website, but I didn't try that.

# Layout Decisions

I initially wanted to make use of the categorization and tagging functionality to separate research, teaching, outreach, etc., and just make one post per topic.  But I couldn't easily figure out how to make Research, Teaching, and Outreach site headers.  I'm sure there is a way to do this, but I found it easier to just remove the fancy, auto-sorting Categories and Tags pages and make new pages with the simple layout.  I guess the outcome is good - this isn't really a blog anyway.

# Font Awesome

I didn't know this existed until there was an example in Minimal Mistakes, but [Font Awesome](https://fontawesome.com/v5.15/icons?d=gallery&p=2&m=free) is really helpful for making little thumbnails. It is important to remember that there are several subclasses, including business (fab) and solid (fas), e.g.
{% highlight html %}
icon: "fas fa-fw fa-envelope"
icon: "fab fa-fw fa-orcid"
{% endhighlight %}
It doesn't look like ADS has one, so I just picked a random one.
