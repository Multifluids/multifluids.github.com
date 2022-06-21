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

### Surface-based geological modelling

IC-FERST uses a surface-based geological modelling (SBGM) workflow that uses NURBS (Non-Uniform Rational B-Splines) surfaces to represent geological heterogeneities without reference to a pre-defined grid. The NURBS surfaces represent a broad range of heterogeneity. The geological model is constructed using the NURBS surfaces and an unstructured mesh created only when required for flow simulation or other calculations. Surface interactions, such as truncation, erosion, stacking or conforming, are enforced to ensure geological relationships are preserved and the boundary representation is watertight (<a href="https://www.onepetro.org/journal-paper/SPE-163633-PA">
          Jackson et al. 2015
       </a> and <a href="https://link.springer.com/article/10.1007/s11004-018-9764-8">
           Jacquemyn et al. 2019
      </a>).

<figure>
  <img src="{{ '/assets/images/meandering_animation02_w800.gif' | absolute_url }}" alt="Surface-based representation of a meandering channel.">
</figure>

The results of <a href="https://doi.org/10.1007/s11004-020-09877-y">
          Osman et al. 2020
       </a> indicate that petrophysical properties of rocks do vary on a point-to-point basis, however this variability is not equivalent to the cell-to-cell variations in flow models. The results presented here indicate that grid-based reservoir models containing many unique values of petrophysical properties (of order hundreds-of-thousands in the examples tested) varying on a cell-to-cell basis can be collapsed into a much smaller number of larger but more geometrically complex domains which are internally homogeneous, irrespective of the reservoir geology, fluid properties or well configuration. Cell-to-cell variability is not necessary to capture flow in reservoir models; rather, it is the spatially correlated variability in petrophysical properties that is important. Reservoir modelling effort should focus on capturing correlated geologic domains in the most realistic and computationally efficient manner.

### Unstructure dynamic mesh optimisation

Dynamic mesh optimisation employs the surfaces that define the boundaries of the geologic
domains with contrasting material properties. The surfaces that define geologic heterogeneity are preserved during adaptivity. The mesh is adapted to provide high resolution to certain fields, for porous media simulations this is normally the pressure and the saturation field (<a href="https://www.onepetro.org/journal-paper/SPE-163633-PA">
          Jackson et al. 2015
       </a>). Moreover, special methods methods have been developed to ensure that the dynamic mesh optimisation can track fronts when modelling with high courant numbers (<a href="https://doi.org/10.1007/s10596-018-9759-z">
          Salinas et al. 2018
       </a>).
      
      
### Robust and mass-conservative formulation

IC-FERST uses a double control volume finite element formulation, which is based on the classical control volume finite element method. 
The formulation in IC-FERST keeps and properties of the classical CVFEM such as mass conservation and the ability to be used with unstructured grids while also providing us with greater robustness against distorted meshes. This latter is fundamental as the aspect ratio of the geological models tend to be very high. The ability to deal with distorted meshes ensures that the in the dynamic mesh optimisation process we do not end up with a mesh that cannot be solved and also enables us to reduce the number of required elements by using bad quality elements in regions where the precision is not very important at certain time (<a href="https://doi.org/10.1002/fld.4381">
           Salinas et al. 2017
      </a>).

IC-FERST formulation also has the following novelties (i) permitting both continuous and discontinuous description of pressure and saturation
between elements; (ii) the use of arbitrarily high-order polynomial representation for pressure and velocity
and (iii) the use of high-order flux-limited methods in space and time to avoid introducing non-physical
oscillations while achieving high-order accuracy where and when possible (<a href="http://onlinelibrary.wiley.com/doi/10.1002/fld.4275/abstract">
           Gomes et al. 2016
      </a> and
      <a href="https://www.sciencedirect.com/science/article/pii/S0021999117307313?via%3Dihub">
           Salinas et al. 2019b
      </a>).      
      
       
### Stable with high Courant numbers

IC-FERST has a new method to admit large Courant numbers. The governing equations are discretized in time using an adaptive theta-method. However, the use of
implicit discretizations does not guarantee convergence of the nonlinear solver for large Courant numbers.
IC-FERST uses a combination of a vanishing artificial diffusion and a non-linear solver based on a double-fixed point iteration method with backtracking. These technologies improve both
convergence and convergence rate (<a href="http://onlinelibrary.wiley.com/doi/10.1002/fld.4357/full">
           Salinas et al. 2016
      </a> and 
      <a href="https://www.sciencedirect.com/science/article/pii/S0045782519304001?via%3Dihub">
           Salinas et al. 2020
      </a>).


### High order mesh to mesh interpolation
IC-FERST implements a higher-order, conservative and bounded interpolation that guarantees mass and energy conservation when interpolatin between meshes. This is of vital importance when using dynamic mesh optimisation.. See <a href="http://www.sciencedirect.com/science/article/pii/S0021999116302030">
           Adam et al. 2016
      </a> for a better explanation.

### Solid fluid coupling
IC-FERST can couple with <a href="http://solidityproject.com/">
           Solidity
      </a> and model the interaction between rock mechanics and fluids. See <a href="http://www.sciencedirect.com/science/article/pii/S0021999116301802">
           Yang et al. 2016
      </a> for a better explanation.



