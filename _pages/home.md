---
layout: splash
permalink: /
hidden: true
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/mm-home-page-feature.jpg
 <!--
  actions:
    - label: "<i class='fas fa-download'></i> Install now"
      url: "/docs/quick-start-guide/"
 -->
excerpt: >
  Planetary scientist, climate change researcher, teacher, student, rock climber.<br />
  <small><a href="https://astro.berkeley.edu/wp-content/uploads/2016/08/cv-2.pdf">Download my CV</a></small>
feature_row:
  - image_path: /assets/images/keck.png
    alt: "research"
    title: "Research"
    excerpt: "I'm interested in planetary atmospheres, planetary rings, extreme precipitation, climate change, radiative transfer, atmospheric dynamics, and interferometry, to name a few."
    url: "{{ site.url }}/research"
    btn_class: "btn--primary"
    btn_label: "See More"
  - image_path: /assets/images/campbell.png
    alt: "teaching"
    title: "Teaching & Service"
    excerpt: "I run a grad-student-focused interdisciplinary climate change seminar, teach planetary science, and help to dismantle oppressive systems."
    url: "{{ site.url }}/teaching"
    btn_class: "btn--primary"
    btn_label: "See More"
  - image_path: /assets/images/tent.png
    alt: "personal"
    title: "Personal"
    excerpt: "I'm an avid rock climber and soccer player/fan, and a proud Midwesterner."
    url: "{{ site.url }}/about"
    btn_class: "btn--primary"
    btn_label: "See More"      
---

{% include feature_row %}