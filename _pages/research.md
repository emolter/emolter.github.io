---
permalink: /research/
title: "Research"
toc: true
header:
  overlay_image: /assets/images/alma-transporters.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Photo credit: [**ALMA Observatory**](https://www.almaobservatory.org/)"
---

# Planetary Science

## Planetary Atmospheres

Observing an atmosphere across the electromagnetic spectrum from the visible to the radio reveals information about clouds, hazes, dust, absorbing gases, and temperature at different pressure levels; radiative transfer modeling provides the translation between an observed spectrum and these physical properties of interest.  The combination of radiative transfer modeling and multi-wavelength observations with cutting-edge (and sometimes amateur!) telescopes led me to (1) discover and characterize a unique storm at Neptune’s equator ([link](https://ui.adsabs.harvard.edu/abs/2019Icar..321..324M/abstract), see also this [Nature Research Highlight](https://www.nature.com/articles/d41586-018-07622-4)), (2) determine isotopic abundances and constrain chemical reaction pathways in Titan ([link](https://ui.adsabs.harvard.edu/abs/2016AJ....152...42M/abstract)), and (3) determine the circulation pattern and gas abundances in Uranus’s middle troposphere ([link](https://ui.adsabs.harvard.edu/abs/2021PSJ.....2....3M/abstract)).

{% capture nepstormimg %}
![Foo]({{ "/assets/images/neptunestorm.jpeg" | relative_url }})
{% endcapture %}

<figure>
  {{ nepstormimg | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Images of Neptune taken during twilight observing revealed an extremely large bright storm system near Neptune's equator (labeled "cloud complex" in the upper figure), a region where astronomers have never seen a bright cloud. The center of the storm complex is 9,000 km across, about 3/4 the size of Earth, or 1/3 of Neptune's radius. The storm brightened considerably between June 26 and July 2, as noted in the logarithmic scale of the images taken on July 2.</figcaption>
</figure>

## The Uranian Ring System

Our ALMA observations of Uranus's atmosphere serendipitously detected thermal emission from the Uranian ring system for the first time!  Some collaborators at the University of Leicester subsequently observed the rings’ thermal emission in the mid-infrared, so we wrote a paper together ([link](https://ui.adsabs.harvard.edu/abs/2019AJ....158...47M/abstract), [press release](https://news.berkeley.edu/2019/06/20/astronomers-see-warm-glow-of-uranuss-rings/)) in which we determined the temperature and filling factor of the rings. We observed the ring system with ALMA again in October 2021 with a factor of 10 higher resolution with the goal to resolve each inner main ring individually; stay tuned for results!

{% capture ringsimg %}
![Foo]({{ "/assets/images/ringsfigure.png" | relative_url }})
{% endcapture %}

<figure>
  {{ ringsimg | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>(a) ALMA and (b) VLT SPHERE images of the Uranian ring system. The ALMA synthesized beam is shown as a grey ellipse in the bottom left corner of (a), and a calibration point source image is shown for the VLT observation in (b). The very bright planet Uranus itself is masked; only with careful u-v plane model planet subtraction and self-calibration can the rings be observed. (c) Brightness temperature measurements of the 	&epsilon; ring (blue points) with a fit to a thermal model overlain (red line). Observations on both sides of the blackbody spectrum permitted strong constraints on the emission temperature of the ring particles themselves.</figcaption>
</figure>

## JWST Observations of Io

under construction, please check back later



## The Twilight Zone at Keck Observatory

I started the Keck Twilight Zone observing campaign ([link to website](https://www2.keck.hawaii.edu/inst/tda/TwilightZone.html)), a long-term project to take short (15-30 minute) observations of Titan, Uranus, Neptune, and Io at near-infrared wavelengths during twilight hours that would otherwise go unused. I spent six weeks at the Keck headquarters in Waimea, Hawaii in the summer of 2017 developing software tools to make these observations easy enough to plan and execute that the Observing Assistants (OAs) could run them without support from our team. This software included a Python-backed Web tool to show the targets' positions and trajectories on the sky compared with the telescope's elevation limits, and csh-based scripts that interacted directly with the telescope and instrument to make running the calibrations and observations a code one-liner. I solicited and incorporated lots of feedback from the OAs who tested those scripts, and the ease-of-use testing paid off: the program has been activated by OAs on over 90 nights since mid-2017. The Twilight Zone project has yielded breakthrough scientific results, including the discovery of a massive storm at Neptunes typically placid equator ([Molter et al. 2019a](https://ui.adsabs.harvard.edu/abs/2019Icar..321..324M/abstract), see also this [Nature research highlight](https://www.nature.com/articles/d41586-018-07622-4)) and a time series of Io volcanism that constrained tidal heat dissipation models ([de Kleer et al. 2019](https://ui.adsabs.harvard.edu/abs/2019AJ....158...29D/abstract)). Im currently co-advising a post-baccalaureate student on a project using Twilight Zone data to explain Neptune’s long-term brightness variations, and more images continue to be taken.


# Climate Change

## Storm Evolution in the U.S. East/Midwest

under construction, please check back later

## Observations of Extreme Precipitation

My recent work focuses on extreme weather and its relationship with climate change on Earth as part of the [CASCADE collaboration](https://cascade.lbl.gov/) at Lawrence Berkeley Lab.  Understanding the response of the precipitation system to climate change is crucial for urban planners, civil engineers, and farmers, who design infrastructure and make decisions based on the amount of rain that will fall in an extreme event.  My most recent paper ([link](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2021GL094697)) made use of Doppler radar observations to improve the way rainfall is quantified, with a particular eye toward extreme rainfall events.  I’m now working on combining the radar data with ERA-5 reanalysis data and GOES satellite imaging to better understand why climate models tend to produce too little heavy precipitation.