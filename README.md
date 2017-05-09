# Particle-Size-Distribution

**Libraries needed:** Pandas, Numpy, glob, matplotlib.pyplot, and from scipy import stats.

Download "raw particle data" file. This file contains contains a number of .xls files. Where ever you save this file make that directory
"path" in python notebook. 


Water samples were taken during summer of 2016 at Stillwater Cove, California at 7m depth. (add GPS point). 
Particles were analysed by 20 fields of view at 100x magnification. Used ImageJ particle analysis package to obtain raw particle data 
(number of particles and area of each) as .xls for each field of view. 

# **Steps**
1. Particle Size Distribution (PSD) code first combines all .xls files within directory and saves as one .csv file. 
1. Transform particle area to Equivalent Spherical Diameter (ESD)
1. Then set histogram bin number and sizes dependent of particle sizes.  
1. Use numpy.histogram to obtain particle counts (ESD) per size bin.
1. Normalize counts/bin by bin width. 
1. Filter normalized counts so there are no zeros. 
1. Function PSD uses parameters to put into optimize.minimize
1. use optimize.minimize to give best fit variables for power equation 
1. Plot scatter of the center of bins(X) and normalized counts(Y) on log.log scale and 
  plot new power equation with variables fromm max.min
