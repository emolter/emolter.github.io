---
title: "UC Berkeley astronomy/EPS thesis with Overleaf"
excerpt_separator: "<!--more-->"
categories:
  - Tutorials
tags:
  - Berkeley
  - software
---

This short tutorial documents how I modified an awesome UCB thesis [Overleaf template](https://www.overleaf.com/latex/templates/uc-berkeley-thesis-template/mfzmtxfqvtxx) to build my own dissertation.  I am not including my own Overleaf document publicly because formatting guidelines from the Grad Div might change over time, and I have no interest in maintaining my own template. But feel free to get in touch and I'll send it to you.

The Berkeley Grad Div's page on [Formatting your Thesis](https://grad.berkeley.edu/academic-progress/doctoral/dissertation/#formatting-your-manuscript) warns, <i>"The most common mistake is following a fellow (or previous) student’s example."</i> This is horrendous advice, and will lead to every student wasting time dealing with nitpicky formatting guidelines.  Thank goodness that LaTex exists, and in particular that Paul Vojta (math professor - never met him) maintains a ucbthesis.cls class file and [Overleaf template](https://www.overleaf.com/latex/templates/uc-berkeley-thesis-template/mfzmtxfqvtxx).  So I used that as my starting point. If you work for the Grad Div and somehow happen to see this, please get in touch! It would be awesome if y'all would maintain a good LaTex template for a science thesis, and I'd be happy to advise.

I needed to import astronomy and earth science publications that were written in LaTex but used classfiles from AAS, Icarus, and GRL, and lots of the LaTex commands I used in those publications did not exist in ucbthesis.cls. I added <code>\usepackage{amsmath}</code> and <code>\usepackage{amssymb}</code>, but there were still many commands (e.g. arcseconds as <code>\arcsec</code> and journal name shortcuts like <code>\grl</code>) missing. For those, I used [latexdefs.tex](https://sites.astro.caltech.edu/observatories/coo/solicit/2022B/latexdefs.tex) (link will download!) from some Caltech Astronomy site (unknown author), and put <code>\include{latexdefs}</code> into the preamble of thesis.tex.  I changed the way Biblatex was handling citations, too; I used <code> \usepackage[style=authoryear-comp, backend=biber, uniquename=false, uniquelist=true, maxcitenames=1]{biblatex} </code>.

I then implemented the following steps to remove/replace formatting from my other publications and convert them into chapters:

<ul>	
  <li> make a new .tex file for the chapter, and copy everything in there </li>
  <li> add the chapter name to the list of <code>\include{}</code> calls in thesis.tex </li>
  <li> remove all calls to begin and end document, remove package imports </li>
  <li> comment out all authors and affiliations </li>
  <li> change <code>\title{}</code> to <code>\chapter{}</code> </li>
  <li> remove calls to <code>\abstract{}</code> </li>
  <li> copy-paste all references into the references.bib, then delete call to bibliography within chapter </li> 
  <li> change citations: <code>\citet{}</code> becomes <code>\textcite{}</code>, and <code>\citep</code> becomes <code>\parencite[][]{}</code> </li>
  <li> import all figures into the Figures directory </li>
  <li> change all the file paths in calls to \includegraphics to point to Figures directory </li>
  <li> fix tables - no fancytable allowed, but can import other packages. see example tables </li>
    <ul> 
  	  <li> <code>\usepackage{longtable}</code> for multi-page tables </li>
          <li> <code>\usepackage{adjustwidth}</code> to move tables left to fit better </li>
	  <li> <code>\usepackage{rotating}</code> for <code>sidewaystable</code> and <code>sidewaysfigure</code> to get tables and figures to fit within margins </li>
	  <li> <code>\footnotesize</code> and <code>\tiny</code> to get tables to fit within margins. The Grad Div is apparently very serious about margins. But they did not complain that the fontsizes were different in different tables, even though I think this is technically against the formatting guidelines.</li>
	  <li> \centering within each table and figure call made things look nice </li>
    </ul>
  <li> remove calls to <code>\acknowledgements</code>, <code>\appendix</code>, <code>\software</code> </li>
  <li> put acknowledgements into the front matter, with text clarifying which chapter(s) certain acknowledgements (e.g. funding) apply to </li>
  <li> Reformat all software citations previously included with <code>\software{}</code>: find DOIs, make BibTeX entries with doi2bib, include them in bibliography and text using <code>\parencite{}</code> </li>
  <li> remove special commands to make appendix numbering like A1, A2, etc. </li>
  <li> Check for places in the text where the margin is violated. This often happens with special text formats like <code>\texttt{}</code> because LaTex doesn't know how to hyphenate it. To fix these, surround the entire paragraph with <code>\begin{sloppypar}</code> and <code>\end{sloppypar}</code> </li>
  <li> try compiling and see what fails </li>
</ul>

At this stage, the document renders successfully and looks pretty good! But the Grad Div gives zero guidelines for how to include published material in the thesis. All they say is <i>"Publishable papers and article-length essays arising from your research project are acceptable only if you incorporate that text into a larger argument that binds together the whole dissertation or thesis. Include introductory, transitional, and concluding sections with the papers or essays."</i> ...the "only" in that sentence a bit ominous. To meet the bare minimum of that requirement, here are the decisions I made to finish formatting stuff. These ended up getting approved without any issues, although I'm sure you could make different decisions that would also be okay:
<ul> 
  <li> At the start of each chapter, I put an italicized note saying, "The published version of this chapter was coauthored by the following people, and is included in the thesis with their express permission: " </li>
  <li> I did actually get email approval from all those people (there is an official way to do this, and the form needs to be submitted like a month before the dissertation deadline. see dissertation filing guidelines) </li>
  <li> Instead of having a chapter section entitled Abstract, I just put the text of the abstract directly after the italicized list of coauthors without any header. <\li>
  <li> I retained sections of each chapter entitled Introduction and Conclusions. I changed the name of the Introduction chapter of the dissertation to be called Background to avoid confusion. </li>
  <li> I wanted to keep the appendices of the different chapters in the chapters themselves. To do so, I just changed all the Appendix chapter sections to be regular sections named "Appendix: whatever." It's an ugly solution and maybe there is a better way, but that's what I went with. I was concerned the Grad Div would make me put them at the end, but they didn't. </li>
  <li> I ended up writing a reasonably long introductory chapter, which contained primarily grad-level textbook material that was relevant to my different chapters. And even though this initially felt like busywork, it was actually really instructive to do and I'm glad I did it.</li>
</ul>

<b> Update 08/15/22 </b>

The dissertation was approved!  I found some problems with the steps I had listed in an earlier version of this blog post, and those have now been changed  to reflect what I actually turned in. I also learned that there's no reason to stress <i>too</i> much about formatting, because if there are small formatting issues after the deadline you are allowed to change them, as long as your full committee has approved the dissertation before the deadline.
