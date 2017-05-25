## Steve

TOTAL: 41.5/45

1.	Reproducibility – another person should be able to run your code, and understand how it works [10/10 points]
  *	Detailed readme file (see above) [4/4 points]
  *	Jupyter notebook contains all necessary sections (see above) [4/4 points]
  *	Git repository is organized and does not contain unnecessary files [2/2 points]

2.	Depth of scientific analysis [10/10 points]
*	Raw data plotted to show variability in space and/or time [1/1 points]
*	Visual comparisons show relationships between different variables [2/2 points]
*	Calculations go beyond raw data (examples: quality control, subsets of data created, variables combined in model calculations) [4/4 points]
*	Appropriate statistical analysis performed to address hypotheses (note: credit given for identifying correct approach, not statistical significance) [3/3 points]

3.	Presentation: Professional delivery, uses effective graphics, and does not use unnecessary text. [5/5 points]
4.	Demonstration that the topic is important (i.e. something that others will care about) [5/5 points]
5.	Completeness of description of the scientific question being investigated [5/5 points]
6.	Clarity of writing, logical progression of ideas [3/5 points]
  * It would help to have more background on the analysis methods, particularly the equation that is being fit to the particle size distributions. It is difficult to tell what is being done just from the code.
7.	Proper citation of outside references from peer-reviewed literature [4/5 points]
  - No list of references at end
8.	Clarity and relevance of information presented in figures [4.5/5 points]
    - Labels, ticks, etc. would improve utility of map

Comments:
- Looks like a good foundation for the rest of the analysis. Since you have a lot more times and depths to look at, it will help to make a plan to incorporate the code from your notebook into a module that can be reused for many samples. Draw a flow chart and put the pieces into functions. I am happy to help with any future programming endeavors.
- Had to add these lines to get map to work:

```
import cartopy.crs as ccrs
import cartopy.io.img_tiles as cimgt
from cartopy.mpl.gridliner import LONGITUDE_FORMATTER, LATITUDE_FORMATTER
```
- You can add errorbars to the box plots by entering an array for the `yerr` option:

```
xstd = [np.std(Clearing), np.std(Kelp), np.std(Artificial)]
plt.bar(y_pos, x, align='center', alpha=0.5, yerr = xstd )
```
