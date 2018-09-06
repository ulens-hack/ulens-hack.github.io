---
layout: default
title: Projects
permalink: /projects/
---

[Home](https://ulens-hack.github.io/)|[Pages](/sitemap/)

_This page will continue to be developed as the Hack Session approaches_

# Project Ideas

A sample of project ideas for the Hack Session. These are meant to be
representative of the _types_ of problems people might be interested
in working on and to help organize ideas about any leg-work that might
be necessary prior to the Hack Session. Projects will be pitched at
the Hack Session. Feel free to draw from this list or to pitch your
own project.

[Modeling Complex Events: General](#modeling-complex-events-general) 
[Modeling Complex Events: Triple Lenses](#modeling-complex-events-triple-lenses)  


# Modeling Complex Events: General

* * *

## Solving Unsolved Events

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

## Weighting Degenerate Solutions

#### Lead
Clement Ranc, David Bennett and volunteers?

#### Suggested Goals
1. Sampling the posterior distribution for a microlensing event
   that have several degenerate solutions.
2. Comparing the marginal distribution on few given parameters
   derived from a regular Metropolis-Hastings algorithm with
   distributions derived from more optimized algorithms.

#### Description
Most analyses presently do little more than weighting the solutions by
the chi^2 to weighting degenerate microlensing model
solutions. However, these degenerate binary lens solutions must be
taken into account in statistical analyses, including on the planets
demography inferred from microlensing detections.

Weighting different microlensing models using the chi^2 works in cases
where the chi^2 surface at each minima has a similar shape or volume,
but with very different chi^2 minima shapes it does not work. We need
methods to properly sample all the relevant chi^2 minima.

Optimized algorithms that might be tested: hamiltonian MCMC, a
hierarchical bayesian algorithm, nested sampling or ...?

#### Requirements
- Public code(s) to generate binary-lens microlensing light curves
  (pyLIMA, MulensModel, muLAn).
- Posterior distribution from an already published paper, or for any
  event we would like to consider. Example of events: MB07192
  (Bennett+2008), OB11950, OB110173 (Poleski+2018, study that already
  includes discussion about exploration methods and use of Nested
  Sampling).
- Optimized MCMC algorithms available and already tested on these events.

#### Outstanding Issues
- Use and test of optimized MCMC algorithms.
- Modeling of not already published data.

#### (Suggested) Homework
- Microlensing friends come with a working code that compute light
  curves for a given set of parameters.
- Statistics friends come with codes that explore high-dimensional
  parameters space, or degenerate parameter space.
- Both try to connect their codes to use the resulting code on one
  event they have chosen (might be from a short-list of chosen
  events).

#### References
Bennett+2008 (2008ApJ...684..663B)
Poleski+2018 (2018arXiv180500049P)

* * *

## Binary Lens Events in UKIRT and KMTNet

#### Leads
Yossi Shvartzvald, Geoff Bryden, Valerio Bozza

#### Goal 
Identify and solve binary microlensing events in the public
UKIRT and KMTNet datasets.

#### Description
Recently, there have been two major releases of microlensing survey
data: UKIRT and KMTNet. These datasets are rich and contain many
unpublished microlensing events, including some two-body events. The
goal is to identify microlensing events with more than one body and
find a preliminary model. These models could be the starting point for
one or more publications.

This project could also be more focused: identify candidate events in
specific categories, e.g. brown dwarf companions, mass measurements
from parallax effects.

#### Outline of Work:
1. Identify interesting events
2. Fit them

#### Outstanding Issues:
- Someone needs to compile a list of published events.
- Modeling events requires significant computer resources.
- Are we doing "by-eye" identification or using an algorithm?
- Need a MulensModel and/or pyLIMA notebook for fitting
- Might also need a data server and/or a way to quickly view many light curves.

* * *

## Alternative algorithms for microlensing modeling

#### Lead
Etienne Bachelet and friends

#### Goals
1. Review of alternative algorithms to find solutions : genetic
algorithms, template matching
2. Exploring new ways to find solutions efficiently and reliably :
machine learning, nested sampling, hamiltonian MCMC....

#### Description
While the standard grid method is extremely intensive in terms of CPU
and already show some weaknesses to find the global minima, it exists
alternative that appear competitive. The goal of this project is to
provide lightcurves to be examinate and fit with alternative
algorithms. A tutorial notebook will be given to easily provide
magnification functions and assimilate. Then, anyone would be able to
investigate his own approach.

#### Requirements
- Public code(s) to generate binary-lens microlensing light curves
(pyLIMA, MulensModel, muLAn).
- Simulated sample of WFIRST-like lightcurves

The pyLIMA team will provide the requirements.

* * *

# Modeling Complex Events: Triple Lenses

## Overview

Triple lenses are an unsolved problem in microlensing of incredible
scientific interest. These are systems consisting of three bodies,
which may correspond to stars with more than one planet or planets in
binary star systems. In the latter case, microlensing has already
found two such systems with very different properties from the
circumbinary planets found by Kepler. At the same time, these
investigations have revealed many complexities in modeling triple lens
events, such as degeneracies between a two planet-one star scenario
and the one planet-two stars scenario. Furthermore, the published work
has necessarily been limited to events that have been solved. There
remain several unsolved microlensing events that may be due to triple
lenses for which solutions have not been found.

Writing the lens equation is simple:

XXX

Solving this equation for the magnification of the source star
(particularly of finite extent) as a function of time is
computationally expensive. This equation can be written as a 10th
order complex polynomial that can be solved numerically. Typically,
this is done using XXX, but it is unstable. Alternatively, one can use
a Monte Carlo to map light rays from the lens plane to the source
plane and count the fraction that fall on the face of the source. This
is extremely computationally expensive and if the grid on the lens
plane is too sparse, it is easy to miss small images, which leads to
inaccuracies in the magnification calculation.

In addition, a triple lens model is defined by N parameters, which
define a highly-correlated likelihood space with multiple minima. This
makes an exhaustive search of parameter space computationally
intractable. So far, known triple lens solutions have generally been
limited to those that are closely approximated by the linear sum of
two two-body solutions. However, many more complex morphologies are
known.

Thus, there are two distinct problems to work on.

* * *

## Triple Lenses: Calculating the Magnification

#### Goal
Discuss numerical methods to robustly solve the three-body lens
equation.

The main issue here is the solution of the 10th order polynomial
equation that yields the solutions of the lens equation. I often find
that this requires calculations in quadruple precision which can slow
down the code significantly. More efficient polynomial solvers or
coordinate transformation that can avoid the need for quadruple
precision could really help.

* * *

## Triple Lenses: Finding All Relevant Solutions

#### Goal

Discuss methods for efficiently and sufficiently searching parameter
space for solutions to light curves created by 3 bodies (minimum of 9
correlated parameters).

#### Known Triple Lens Planets
- ob06109:  1 star, 2 planet lenses, modeling easy
- ob08270:  satisfactory solution not yet found. Likely 1 star, 1 plane, and 1 planet or star lens
- ob07349:  circumbinary planet
- ob08092:  2 stars, 1 planet, wide separations, modeling trivial
- ob120026: 1 star, 2 planet lenses
- ob130341: 2 stars, 1 planet - some ambiguity about whether the planet orbits 1 or 1 stars
- ob141722: 1 star, 2 planets - modeling trivial
- ob160613: multiple solutions - not all in the published paper, some are binary source, binary lens
            MOA data covers 1st caustic crossing, but is not in paper. 

Some of these have data available on the Exoplanet Archive.

2 of the more difficult events include data that is non-public. We
could try to make this data public by the time of the Hack Session, or
at least release it to participants. These are:
- ob07270: proprietary data from OGLE, uFUN, and PLANET
- ob160613: proprietary data from MOA (other data is published).

#### References
- (http://adsabs.harvard.edu/abs/2015ApJ...806...63D)
- (http://adsabs.harvard.edu/abs/2015ApJ...806...99D)
- papers corresponding to the planets above

#### Outstanding issues
- Obtaining data for these events
  - Some are on the Exoplanet Archive
  - Some are published but not (yet) on the Archive
  - Some are proprietary --> Need publication agreement

* * *

# Open Science Questions

## Science Questions
- Where is the snow line? 
- What are the theoretical explanations for the planets we see?
- What the theoretical expectations for what we should see?
- Projecting known planet populations into WFIRST detection space.

## Synergies with TESS, Gaia
- How do microlensing planet populations compare with those inferred
  (or to be inferred) with TESS or Gaia?

# Developing Tools

* * *

## Ray-Shooting Algorithm

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

## Map-making code

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

## Jupyter Binary Fitting

#### Goal
Create a _Jupyter_ notebook using _MulensModel_ that robustly finds
solutions to binary microlensing events.

#### Notes
- Maybe one for identifying point lenses that need more parameters?

* * *

## Create a Galaxy Zoo-type project for UKIRT data

#### Lead
TBD

#### Goal
Create a Galaxy Zoo project to classify UKIRT light curves

#### Description
The Galaxy Zoo platform uses "citizen scientists" to classify objects
in large datasets. We could use this platform to create a project to
classify UKIRT light curves as microlensing/not microlensing,
regular/irregular variable, flat, and anomalous/point lens
microlensing. Having a large set of human-classified objects would
give us a check on the completeness and reliability of the algorithms
used to identify microlensing events. For example, the algorithm used
for UKIRT events is designed for finding point-source--point-lens
events. Although it does find binary lenses, we don't know how
complete it is for such objects. We could also consider injecting fake
microlensing events into the UKIRT dataset to better understand our
completeness.
