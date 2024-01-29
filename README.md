# Protostars_FERIA
A repository for materials used in the FERIA project used in Milne et. al. 2024

I developed this code during my 2023 REU at the University of Texas, Austin. I worked alongside Dr. Dominique Segura-Cox and Prof. Stella Offner on Modeling Infall and Rotation of 10 Class 0/I Protostars to Measure Mass and Disk Radii
This project used FERIA (Oya et al. 2022) to generate models of protostellar disks as cube FITS files, compare them to observed data from ALMA in the C18O (2-1) band, and compute the "best models" and their parameters.
We accomplished this by a grid search method across 4 parameters: Protostellar Mass, Disk Inner Radii, Disk Outer Radii, and Centrifugal Barrier.
  Protostellar Mass represents the mass of the protostar at the center of the disk. Generally we sampled from .1-1.5 M_sun, in increments of .1 M_sun, with some exceptions extending the range to 3 M_sun
  Disk Inner Radii represents the innermost edge of the circumstellar disk. We sampled from 1-400 AU, in increments of 100 AU. 0 AU was undefined, so we use 1 AU as 0
  Disk Outer Radii represents the edge of our model. While this can represent the circumstellar disks outermost edge, it may be the influence of the star on its environment. We sampled from 300-1000 AU, in increments of 100 AU
  Centrifugal Barrier radius represents the turnover point for gas inflow models. Within it, gas follows Keplerian Rotation. Beyond it, gas follows an Infalling Rotating Envelope model. We sampled from 1-1000 AU, in increments of 50 AU

Code is shared between my personal Jupyter Notebooks, and some C files used by FERIA. Small modifications to the C files were made to exclude modeling scenarios outside of Rin <= CB <= Rout generally, or to set CB to Rin or Rout depending on scenario.
