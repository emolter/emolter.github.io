---
title: "How to: UCB astro/EPS/physics thesis with Overleaf"
excerpt_separator: "<!--more-->"
categories:
  - Tutorials
tags:
  - Berkeley
  - software
---

This short tutorial documents how I modified an awesome UCB thesis [Overleaf template](https://www.overleaf.com/latex/templates/uc-berkeley-thesis-template/mfzmtxfqvtxx) to build my own dissertation.  I am not including my own Overleaf document for you to copy because formatting guidelines from the Grad Div might change over time and I have no interest in maintaining my own template.

The Berkeley Grad Div's page on [Formatting your Thesis](https://grad.berkeley.edu/academic-progress/doctoral/dissertation/#formatting-your-manuscript) warns, "The most common mistake is following a fellow (or previous) student’s example." This is horrendous advice, and will lead to every student wasting time dealing with nitpicky formatting guidelines.  Thank goodness that LaTex exists, and in particular that Paul Vojta (math professor - never met him) maintains a ucbthesis.cls class file and [Overleaf template](https://www.overleaf.com/latex/templates/uc-berkeley-thesis-template/mfzmtxfqvtxx).  So I used that as my starting point.

I needed to import astronomy and earth science publications that were written in LaTex but used classfiles from AAS, Icarus, and GRL, so lots of the commands did not exist in ucbthesis.cls. So I put <code>\usepackage{amsmath}</code> and <code>\usepackage{amssymb}</code>, but there were still many commands (e.g. arcseconds as <code>\arcsec</code> and journal name shortcuts like <code>\grl</code>) missing. For those, I used [latexdefs.tex](https://sites.astro.caltech.edu/observatories/coo/solicit/2022B/latexdefs.tex) (link will download!) from some Caltech Astronomy site (unknown author), and put <code>\include{latexdefs.tex}</code> into the preamble of thesis.tex.

I implemented the following steps to remove/replace formatting from other publications:

<ul>	
  <li> add the chapter name to list of <code>\include{}</code> calls in thesis.tex </li>
  <li> remove all begin and end document, package imports </li>
  <li> comment out all authors and affiliations </li>
  <li> change <code>\title{}</code> to <code>\chapter{}</code> </li>
  <li> change <code>\abstract{}</code> to <code>\section{Abstract}</code> </li>
  <li> copy-paste all references into the references.bib </li>
  <li> change citations: <code>\citet{}</code> —> <code>\textcite{}</code>, <code>\citep</code> —> <code>\cite{}</code> </li>
  <li> import all figures into the Figures/ directory </li>
  <li> change all calls to \includegraphics to look in Figures/ </li>
  <li> fix tables - no fancy tables allowed - see example tables </li>
    <ul> 
	  <li> make all tables same size! <code>\footnotesize</code> right after <code>\begin{table}</code> </li>
  	  <li> <code>\usepackage{longtable}</code> for multi-page tables </li>
      <li> <code>\usepackage{adjustwidth}</code> to move tables left to fit better </li>
	</ul>
  <li> remove calls to <code>\acknowledgements</code>, <code>\appendix</code>, <code>\software</code> </li>
  <li> put acknowledgements into the front matter, with text clarifying which chapter(s) certain acknowledgements (e.g. funding) apply to </li>
  <li> Reformat all software citations previously included with <code>\software{}</code>: find DOIs, make BibTeX entries with doi2bib, include them in bibliography but not text using <code>\nocite{}</code> </li>
  <li> remove special commands to make appendix numbering like A1, A2, etc. </li>
  <li> try compiling and see what fails </li>
</ul>

At this stage, the document renders and looks pretty good! But because the Grad Div is stuck in like 1950 and thinks a thesis should be a single, nicely-flowing, standalone document that is more important than publications in journals, they give zero guidelines for how to include published material in the thesis. All they say is <i>"Publishable papers and article-length essays arising from your research project are acceptable only if you incorporate that text into a larger argument that binds together the whole dissertation or thesis. Include introductory, transitional, and concluding sections with the papers or essays."</i> ...the "only" in that sentence a bit ominous. To meet the bare minimum of that requirement, or at least make the Grad Div think I did, some decisions are yet to be made:
<ul> 
  <li> Is it okay to have sections of each chapter entitled Abstract, Introduction, and Conclusions? Should I rename them to look less conspicuously copy-pasted from published work and more like "transitional" sections? Do I need to remove the abstracts? </li>
  <li> Where should I put the Appendices of all the chapters? At the end of the entire document? Within the chapters? Should they be labeled as appendices? </li>
  <li> What do I put in the thesis's overall abstract? </li>
  <li> What do I write in the introductory chapter of the thesis? </li>
</ul>

Once again due to the fact that they are behind the times, the University does not provide any guidelines on how to credit coauthors. These days, at least in most science fields, the lead author does 99 percent of the work for a given paper but the author list includes people who (to list a few examples) provided help with software the author used in the analysis, donated observing time, wrote the proposal to get observing time used in the paper, ran data through a pipeline, or made a single figure. In my opinion the thesis should be reimagined to reflect the collaborative nature of science in more ways than just this one, but that's a different discussion.  For now, I just removed all formatting from the author list and put the following text in italics at the start of each chapter: <i>"The published version of this chapter was coauthored by the following individuals, and is included in this thesis with their express permission: Author One, Author Two, ..."</i> Hopefully this satisfies the Grad Div.
