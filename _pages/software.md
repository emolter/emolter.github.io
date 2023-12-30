---
permalink: /software/
title: "Open-Source Software Projects"
toc: true
header:
  overlay_image: /assets/images/rho-ophiuchi.png
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Photo credit: [**STScI**](https://webbtelescope.org/home)"
---

I recently accepted a position as a science software engineer at Space Telescope Science Institute; more updates on that soon! The projects below are pieces of open-source code I contributed as a grad student and postdoc at Berkeley.

# Pylanetary

I am the founder and primary maintainer of the pylanetary package. 
The idea behind pylanetary is to bring solar system science tools into 
the open-source Python 3 / Astropy ecosystem. Most solar system researchers 
rely heavily on useful code snippets passed down from other scientists, 
but these pieces of code are untested, in multiple languages, closed-source, 
and have many untracked dependencies. In many ways, solar system research lags
behind other areas of astrophysics in its adoption of the open-source philosophy.
Pylanetary aims to help fix that.
The eventual goal is to become Astropy-affiliated, but that is a long way off. 
We would love your help developing it!
See the [readthedocs page](https://pylanetary.readthedocs.io/en/latest/).

# Keck Imaging Data Reduction Pipeline

I wrote a pipeline for processing data from Keck's NIRC2 and OSIRIS imagers.
While this pipeline was originally used to make quick-look images of solar system
objects for the [Keck Twilight Zone observing campaign](https://www2.keck.hawaii.edu/inst/tda/TwilightZone.html#), it is designed to be
general-purpose, and is now advertised on [Keck's software tools website](link).
See the [readthedocs page](https://nirc2-reduce.readthedocs.io/en/latest/?badge=latest).


# Astroquery PDS Query Tool

I wrote a tool to query the Planetary Data System's Ring-Moon Systems Node, and contributed it to Astroquery. This was my first major contribution to an open-source project, and I learned a ton from the feedback I received in the process!
See the [readthedocs page](https://astroquery.readthedocs.io/en/latest/solarsystem/pds/pds.html).


# Astropy WCS Compass

I pitched a hack day project at .Astronomy 12 to make our first contribution to Astropy, which I was later told is a classic .Astronomy hack day activity. Eilat Glikman turned this nebulous idea concrete by pointing out that Astropy lacks the obvious functionality to overlay a WCS compass onto images. We agreed that this was a slam-dunk for astropy.visualization. Our team was Lindsey Gordon, Sam Vaughan, Eilat Glikman, Thomas Vandal, and me, and we had some discussions with Ella Roselli, Brett Morris, and Peter Scicluna. After much discussion of the best way to determine where sky North was in any given WCS, we were able to submit the initial pull request by the end of one long day. Happily, this feature will be added to the next Astropy release!

