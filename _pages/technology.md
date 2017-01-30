---
permalink: /technology/
title: "Numerical technology"
excerpt: ""
layouts_gallery:
  - url: /assets/images/mm-layout-splash.png
    image_path: /assets/images/mm-layout-splash.png
    alt: "splash layout example"
  - url: /assets/images/mm-layout-single-meta.png
    image_path: /assets/images/mm-layout-single-meta.png
    alt: "single layout with comments and related posts"
  - url: /assets/images/mm-layout-archive.png
    image_path: /assets/images/mm-layout-archive.png
    alt: "archive layout example"
---

### NURBS representation of geology

IC-FERST uses a surface-based geological modelling (SBGM) workflow that uses NURBS (Non-Uniform Rational B-Splines) surfaces to represent geological heterogeneities without reference to a pre-defined grid. The NURBS surfaces represent a broad range of heterogeneity. The geological model is constructed using the NURBS surfaces and a mesh created only when required for flow simulation or other calculations. Surface interactions, such as erosion, stacking or conforming, are enforced to ensure geological relationships are preserved and the boundary representation is watertight. See  <a href="https://www.onepetro.org/journal-paper/SPE-163633-PA">
          Jackson et al. 2015
       </a> and <a href="http://www.earthdoc.eage.org/publication/publicationdetails/?publication=86330">
           Jacquemyn et al. 2016
      </a> for more details.

### Unstructure dynamic mesh optimisation

Dynamic mesh optimisation employs the surfaces that define the boundaries of the geologic
domains with contrasting material properties. The surfaces that define geologic heterogeneity are preserved during adaptivity. The mesh is adapted to provide high resolution to certain fields, for porous media simulations this is normally the pressure and the saturation field.  See <a href="https://www.onepetro.org/journal-paper/SPE-163633-PA">
          Jackson et al. 2015
       </a> and <a href="https://www.onepetro.org/conference-paper/SPE-173279-MS">
          Salinas et al. 2015
       </a> for more details.

### Stable with high Courant numbers

IC-FERST has a new method to admit large Courant numbers. The governing equations are discretized in time using an adaptive theta-method. However, the use of
implicit discretizations does not guarantee convergence of the nonlinear solver for large Courant numbers.
IC-FERST uses a double-fixed point iteration method with backtracking, which improves both
convergence and convergence rate. See <a href="http://onlinelibrary.wiley.com/doi/10.1002/fld.4357/full">
           Salinas et al. 2016
      </a> for more information.

### High order methods

IC-FERST is based on a
control volume finite element mixed formulation and new force-balanced finite element pairs. The novelty
of the method lies in (i) permitting both continuous and discontinuous description of pressure and saturation
between elements; (ii) the use of arbitrarily high-order polynomial representation for pressure and velocity
and (iii) the use of high-order flux-limited methods in space and time to avoid introducing non-physical
oscillations while achieving high-order accuracy where and when possible. 
See <a href="http://onlinelibrary.wiley.com/doi/10.1002/fld.4275/abstract">
           Gomes et al. 2016
      </a> for more details.

### High order mesh to mesh interpolation
IC-FERST implements a higher-order, conservative and bounded interpolation for the dynamic and
adaptive meshing of control-volume fields dual to continuous and discontinuous finite
element representations. See <a href="http://www.sciencedirect.com/science/article/pii/S0021999116302030">
           Adam et al. 2016
      </a> for a better explanation.

### Solid fluid coupling
IC-FERST can couple with FEMDEM and model the interaction between rock mechanics and fluids. See <a href="http://www.sciencedirect.com/science/article/pii/S0021999116301802">
           Yang et al. 2016
      </a> for a better explanation.



