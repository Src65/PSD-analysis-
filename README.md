# Particle-Size-Distribution

**Libraries needed:** Pandas, Numpy, glob, matplotlib.pyplot, scipy, from scipy import stats, from cartopy.io import shapereader.

Download "[all_raw particle data](/all_raw_data.zip)" file. Make this a sub directory from jupyter directory. This file contains contains a number of .xls files. Where ever you save this file make that directory "path" in python notebook.

Download "[SWC_map_files](/SWC_map_files.zip)" for map figure 1.  



Water samples were taken during summer of 2016 at Stillwater Cove, California at 7m depth. (add GPS point). 
Particles were analysed by 20 fields of view at 100x magnification. Used ImageJ particle analysis package to obtain raw particle data 
(number of particles and area of each) as .xls for each field of view. Image processing code available [here](/Particle_ImageJ_script.txt) 

# **Steps**
1. Load libraries: Pandas, Numpy, glob, matplotlib.pyplot, scipy, and from scipy import stats
1. Particle Size Distribution (PSD) code first combines all .xls files within directory and saves as one .csv file
1. Transform particle area to Equivalent Spherical Diameter (ESD)
1. Then set histogram bin number and sizes dependent of particle sizes  
1. Use numpy.histogram to obtain particle counts (ESD) per size bin
1. Normalize counts/bin by bin width
1. Filter normalized counts so there are no zeros
1. Function PSD uses parameters to put into optimize.minimize
1. use optimize.minimize to give best fit variables for power equation from output variable "x"
1. Plot scatter of the center of bins without empty bins(X) and normalized counts(Y) without zeros on log.log scale and 
  plot new power equation with variables fromm max.min  where output is x =[#, #] first term is scaler A and second term is slope B in       equation  Y= A(mid_bins_nozero)^B
1. Add variables A and B to total_particle file
1. Pull all slope data for and seperate by treatment
1. Run one way ANOVA for slope between treatments
