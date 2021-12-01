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

Update 11/30: I'd highly recommend setting up a Docker environment to host a local copy of the site as it makes everything easier. You can learn how in [Part II of this tutorial]({{ site.url }}/tutorials/website-build-ii). Although it should have been in Part I, I didn't figure out how to do it until just now.

# Software prerequisites

GitHub supports building websites using [Jekyll](https://jekyllrb.com/). Jekyll was easy to install with just 
{% highlight bash %}
gem install jekyll bundler
{% endhighlight %}
once I had installed the appropriate Ruby versions. Ruby was the hard part, as it seems pretty annoying to install without homebrew and the version on my Mac was outdated (need at least 2.5). I used the rbenv ruby environment handler, and had to install it by hand via [these instructions](https://github.com/rbenv/rbenv#basic-github-checkout) because I don't use homebrew. Once that was done, I was able to just run
{% highlight bash %}
rbenv install 2.7.4
{% endhighlight %}


<!--more-->

# The Minimal Mistakes template

Now I needed a Jekyll template since the default from GitHub Pages seemed a bit simplistic. [Minimal Mistakes](https://github.com/mmistakes) came through bigtime. I spent a long time trying to use a different free Jekyll template, but its homepage was kind of dumb-looking and I couldn't figure out easily how to change it. The fact that Minimal Mistakes had a [quickstart](https://github.com/mmistakes/mm-github-pages-starter/generate) that made the GitHub repo for me was pretty awesome. All I did was take that, git clone it to my local machine, and start making changes! Then I just git commit as normal. It takes a few minutes for the site to update after the GitHub repo updates. It looks easy to change any layouts or settings by simply copying relevant layout or style files from the main Minimal Mistakes repo into my local repo (the local repo's version overrides the defaults), but I didn't try that yet.

I initially wanted to make use of the categorization and tagging functionality to separate research, teaching, outreach, etc., and just make one post per topic.  But I couldn't easily figure out how to make Research, Teaching, and Outreach into site headers as well as blog categories.  I'm sure there is a way to do this, but I found it easier to just remove the fancy, auto-sorting Categories and Tags pages and make new pages with the "simple" layout.  I guess the outcome is fine - this isn't really a blog anyway - but the search function is pretty limited as it seems to only see blog posts.

I wanted to change the homepage to be something other than the blog posts, since this is mainly a professional website. Minimal Mistakes already had that solved, too: they provide a splash page layout [here]{https://raw.githubusercontent.com/mmistakes/minimal-mistakes/master/docs/_pages/home.md}. To use this, I put it in _pages/home.md, then deleted index.html in the root directory. I really enjoy that the homepage is primarily photos, but one could also make a home.md with the "simple" layout or whatever.

# Font Awesome

I didn't know this existed until there was an example in Minimal Mistakes, but [Font Awesome](https://fontawesome.com/v5.15/icons?d=gallery&p=2&m=free) is really helpful for making little thumbnails. You should see where these go in the _config.yml file; the base Minimal Mistakes template is already using them. It is important to remember that there are several subclasses, including business (fab) and solid (fas), e.g.
{% highlight html %}
icon: "fas fa-fw fa-envelope"
icon: "fab fa-fw fa-orcid"
{% endhighlight %}
It doesn't look like ADS has a Font Awesome icon, so I just picked a random one.  But these really go a long way toward making things look professional.
