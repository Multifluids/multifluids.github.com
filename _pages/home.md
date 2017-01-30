---
layout: splash
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/mm-home-page-feature.jpg
  cta_label: "<i class='fa fa-download'></i>Get it Now"
  cta_url: "/license/"
  caption:
excerpt: 'IC-FERST is the next generation reservoir simulator based on Control-Volume Finite Element methods and dynamic unstructured mesh optimisation.
<br /> <small><a href="https://github.com/Multifluids/multifluids">Private repository</a></small><br /><br /> {::nomarkdown}{:/nomarkdown}'
feature_row:
  - image_path: /assets/images/mm-surface-based.png
    alt: "customizable"
    title: "Surface based modelling"
    excerpt: "Petrophysical properties are represented mesh free by using NURBS surfaces."
    url: "/technology/"
    btn_label: "Learn More"
  - image_path: /assets/images/mm-simulation.png
    alt: "State-of-the-art"
    title: "State-of-the-art numerical technology"
    excerpt: "Dynamic mesh optimisation, high order methods, novel discretizations, resilient against 'poor' quality meshes, etc. "
    url: "/examples/"
    btn_label: "Learn More"
  - image_path: /assets/images/mm-OpenSourceLogo.png
    alt: "100% free"
    title: "Code license"
    excerpt: "IC-FERST is free to use and is licensed under the LGPL."
    url: "/license/"
    btn_label: "Learn More"
github:
intro:
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}





# Applications

IC-FERST is an open source multiphase simulation tool that is able to solve the Darcy and the Navier-Stokes equations in 2 and 3 dimensions. It uses dynamic unstructured mesh optimisation and has been parallelized using MPI and also has been tested on the U.K. national super computer Archer. IC-FERST has been used for the following scientific areas: Porous media and inertia dominated flows, interfacial tension flows, viscous fingering, flooding and rock fracturing.

