---
title: "Making this website part II"
excerpt_separator: "<!--more-->"
categories:
  - Tutorials
tags:
  - website
  - jekyll
---

This is part two of my website build using [Jekyll](https://jekyllrb.com/) with the [Minimal Mistakes](https://github.com/mmistakes) template and hosted by Github Pages. In the [previous edition]({{ site.url }}/tutorials/website-build) I was able to get something reasonable up and running using the Minimal Mistakes [quickstart](https://github.com/mmistakes/mm-github-pages-starter/generate). The goals here are to (1) use Docker to make a local copy of the website so I don't have to git push every time I want to test a change, and (2) to change some Minimal Mistakes defaults to personalize the site's look. The repo that underlies the website is [here](https://github.com/emolter/emolter.github.io). In this post I'm basically following Katerina Bosko's [very nice tutorial](https://www.cross-validated.com/Personal-website-with-Minimal-Mistakes-Jekyll-Theme-HOWTO-Part-I/) parts I and II, with the twist that I'll try to make as few changes as possible from the quickstart site.

# Locally serving the website using Docker

A [Docker](https://www.docker.com/) container is used to run the virtual environment where the local version of the website lives. Installing Docker was super easy: I just downloaded the disk image and dragged it to the Applications folder, and the command-line tools worked automagically (<code>which docker</code> pointed to the correct path with no extra steps needed).  Going through the Docker tutorial was helpful. One lesson was that if you try to initialize a container on a port that's in use, the container will fail to run (of course), but Docker will still allocate a container name and ID that must be deleted before remaking it. You can see a list of containers with 
{% highlight html %}
docker ps -aq
{% endhighlight %}
and remove all of them with 
{% highlight html %}
docker rm -f $(docker ps -aq)
{% endhighlight %}

Once Docker was installed, I followed Katerina Bosko's tutorial Part I exactly, replacing instances of <code>/usr/src/app</code> with the path to the directory where my site sits (e.g. <code>/Users/emolter/emolter.github.io/</code>). Since I was starting with an already-functional website based on the quickstart instead of with a clone of the full Minimal Mistakes site, I also had to copy <code>minimal-mistakes-jekyll.gemspec</code> into the directory to make everything work.

As advertised, I can now instantly see any changes I make to the site upon refreshing <code>http://0.0.0.0:4000/</code>. To make changes to any of the .yml files, it's necessary to rerun the following lines:
{% highlight html %}
docker build -t personal-website .
docker run --volume="$PWD:/Users/emolter/emolter.github.io" -p 4000:4000 -t personal-website
{% endhighlight %}


<!--more-->

# Styling on em

The Minimal Mistakes quickstart is nice because it makes a pared-down version of the site that does not include any of the style files, which makes it user-friendly for a newbie like me. I'm not quite sure how this works, but apparently just setting <code>remote_theme: mmistakes/minimal-mistakes</code> in your <code>config.yml</code> file means Jekyll/Github Pages will find all the style files remotely. But now I want to make changes to that remote theme.  Importantly, if style files are included inside a site with a remote theme, then Jekyll will look inside the site first and override the remote theme defaults. So making changes is as simple as copying the relevant style file from the Minimal Mistakes base repository into your site and then changing whatever you want. Just make sure to preserve the directory structure (e.g., use <code>_sass/minimal-mistakes/_sidebar.scss</code> to change the sidebar.)

I liked the way the sidebar looks on Katerina Bosko's site with the larger picture, so I did indeed copy over <code>_sass/minimal-mistakes/_sidebar.scss</code>. For anything within sass, I also learned it is necessary to copy <code>_sass/minimal_mistakes.scss</code> or else your changes won't be seen. 

I didn't make any more changes because the defaults look good enough for me, but the proof-of-concept is there and any changes I want to make later should be easy.

# Pushing changes to GitHub

I was initially concerned that all these changes to the GitHub repo would mess up the way the real site at <code>emolter.github.io</code> behaves. Apparently running the naive
{% highlight html %}
git add -A
git commit -m "whatever"
git push
{% endhighlight %}
doesn't break anything, and correctly updates content within existing pages as well as including new blog posts or pages, but does not incorporate the style changes I made.

The solution is simply to remove <code>_site</code> from <code>.gitignore</code>, then do the usual git push.


