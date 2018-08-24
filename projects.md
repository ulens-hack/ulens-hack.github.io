---
layout: default
title: Projects
permalink: /projects/
---

# Projects

## 1a. Map-making code

#### Leads
Radek Poleski and Jennifer Yee

#### Goal
Write a module to calculate the magnification of a binary
lens using the map-making method.

#### Description
Map-making is one method for numerically calculating the magnification
of a finite source. This is essentially a Monte Carlo method in which
~10^7 light rays are "shot" from the image (lens = planet host star)
plane and collected and counted on the source plane. The magnification
of the source is then proportional to the number of rays contained
within the boundary of the source. Typical routines use a hexagonal
grid on the source plane with many resolution elements relative to the
size of the source.

#### Outline of Work

1. Define use cases
  - Write a use case for finding best-fit parameters for a
    high-magnification event.
  - Discuss various features of map-making code, e.g.
        - ability to plot the resulting magnification map
        - fixed s, q
        - usually used for high-magnification events because the relevant
          areas in both the source and image planes are well known.
  - Outline the parameters, methods, and interface with _MulensModel_
  - Consider avenues for future development (which might affect the
    architecture), e.g.
        - expanding the map if the original definition was too small
2. Write unit tests
3. Write methods

#### Outstanding Issues:
- Need to identify a test data set/set up some comparisons to existing
  magnifcation calculations.
- What language should it be written in? Maybe prototype in Python and
  then re-write in C? (We would need a C programmer)
- Need to prepare a brief presentation explaining the physics.
- Do we start with the high-mag case?
- Do we write some kind of checker for numerical accuracy?
- How much of the use cases need to be done *before* the Hack Session?

* * *

## 1b. Ray-Shooting Algorithm

#### Lead
Radek Poleski

#### Goal
Write a module for _MulensModel_ to calculate the magnification
using the ray-shooting method.

#### Description
One difficulty in accurately calculating the magnification of a finite
source is to locate all of the images, especially if one or more of
them is small. Using the ray-shooting method, we know that if one
light ray falls on one side of the source and another one falls on the
other side, there must be a light ray in between that falls directly
on the source. A method that incorporates this information could
result in gains in efficiency and accuracy over other methods by
identifying all of the images and only shooting rays densely in the
regions of those images.

#### Outline of Work
1. Write use cases.
2. Write unit tests.
3. Write module.

#### Outstanding Issues
- All of the issues listed for the Magnification Map Project.
- The description needs to be written and revised by Radek.
- We can't do both this and the Magnification Map because both require Radek.

* * *

## 1c. Jupyter Binary Fitting

#### Goal
Create a _Jupyter_ notebook using _MulensModel_ that robustly finds
solutions to binary microlensing events.

#### Notes
- Maybe one for identifying point lenses that need more parameters?

* * *

## 2a. Solving Unsolved Events

#### Lead
Radek Poleski

#### Goal
One of the science projects for Microlensing Hack Session could
be re-analysis of the events for which proper microlensing model was
not found yet.

#### Description
For example, one of the binary microlensing events detected by Gaia, i.e.,
Gaia16aye has very complicated light curve
([Wyrzykowski et al. 2017](http://adsabs.harvard.edu/abs/2017MNRAS.465L.114W)).
It shows four caustic crossings and two cusp approaches. The model
that well explains all these features has not yet been found.

I think Dave Bennett has additional data for ob04367=mb04033. This event
was already published with OGLE data only
([Jaroszynski et al. 2006](http://adsabs.harvard.edu/abs/2006AcA....56..307J))
 and additional data suggest 2S2L or 1S3L model.

In addition, there are a few events for which published models do not
fully explain the observed light curves, but the models fitted had a
few simplifications. These are:
- **OGLE-2003-BLG-220** = **OGLE-1999-BLG-42** (Skowron et al. 2009),
- **OGLE-2005-BLG-331** (Skowron et al. 2007),
- **OGLE-2007-BLG-327** (Jaroszynski et al. 2010).

#### Outstanding Issues
- Obtaining data for these events

* * *

## TODO: More projects
