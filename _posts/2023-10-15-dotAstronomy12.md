---
title: ".Astronomy 12 Debrief"
excerpt_separator: "<!--more-->"
categories:
  - Professional Development
  - Personal
tags:
  - conferences
  - software
  - personal
---

de-briefer de-better, har, har.

# I Contributed!

In contrast to the Astronomical Software Development conference last year, which was my first unconference, this time around at .Astronomy 12 I knew the drill and felt empowered to contribute some stuff!

## First Astropy Contribution (Hack Day Project)

I pitched a hack day project to make our first contribution to Astropy, which I was later told is a classic .Astronomy hack day activity. Eilat Glikman turned this nebulous idea concrete by pointing out that Astropy lacks the obviously-useful and ubiquitous functionality to overlay a WCS compass onto images. We agreed that this was a slam-dunk for astropy.visualization. Our team was Lindsey Gordon, Sam Vaughan, Eilat Glikman, Thomas Vandal, and me, and we had some discussions with Ella Roselli, Brett Morris, and Peter Scicluna. After much discussion of the best way to determine where sky North was in any given WCS, we were able to submit the initial pull request by the end of one long day. Happily, this feature will be added to the next Astropy release! [Link to pull request](https://github.com/astropy/astropy/pull/15434)

## Showyourwork! Tutorial Unconference Session

The incredible [showyourwork!](https://show-your.work/en/latest/) workflow for open-sourcing an entire scientific publication, built by Rodrigo Luger (and others), was the coolest thing I took away from the last unconference. This year, I proposed to facilitate an unconference session about it, and it got voted for! We combined it with a [snakemake](https://snakemake.readthedocs.io/en/stable/) tutorial facilitated by Sam Vaughan. The session seemed successful, mostly because .Astronomy participants are a super engaged audience.

## Extra-Short LaTeX References

This unconference coincided with my first postdoc application deadlines, and I had run into a problem while finishing those up: I couldn't find a LaTeX .bst style for hyper-condensed references. These are necessary whenever there is a page limit for a proposal, and any scientist who's written, e.g., a JWST proposal knows this pain (why bibliographies are still included in page limits is beyond me). During the second hack day, Yasmeen Ayali and I drafted a very basic ultra-condensed biliography bst file. We had no idea what we were doing coding that, but were able to Google around enough to hack a minimal example together. If you (or future me) runs across this post, knows a bit more what they are doing writing hardcore LaTeX, and wants to improve it, Yasmeen and I would be extremely thankful! [Here is the link.](https://github.com/emolter/xtrashort-refs)


# I Learned! (Tips & Tricks)

## VSCode and Extensions

Before this workshop, my IDE of choice had been TextMate, a free alternative to SublimeText. I say choice, but really I Googled "free sublimetext" in my first year of grad school and learned how to use TextMate, which is pretty basic but not bad overall. This workshop opened my eyes to the power of VSCode, though - wow! Exploring all the extensions, plus GitHub Copilot, have led to a dramatic overhaul in the way I write software.

## Copier

I learned about a new way to create new packages called [copier](https://copier.readthedocs.io/en/stable/). It looked like this tool would make packaging my Python code much, much easier! I'm looking forward to trying it.

## One-liners

<code>git add -U</code> will track all edited documents, but will not start tracking new/untracked documents


# I Had Fun!

I met (or re-met) tons of amazing people! Here's a photo of us presenting our Hack Day project:

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/dotAstronomy.jpg" alt="Hack Day" width="400">

