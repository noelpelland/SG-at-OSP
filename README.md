# SG-at-OSP
MATLAB code for loading and manipulating data from Seaglider surveys at Ocean Station Papa.

Noel Pelland
nap2@u.washington.edu
noel.pelland@noaa.gov

The script OSP_SG_surveys_bin_data_load_and_plot.m is intended as an introduction of how to load and plot Seaglider profiling and depth-average current data from surveys at Ocean Station Papa, available from the University of Washington ResearchWorks archive at: http://hdl.handle.net/1773/41656.

If OSP_SG_surveys_bin_data_load_and_plot.m is run successfully, it will generate six figures which are reproductions from research articles about these Seaglider surveys that have recently been published or submitted.  If printed as PDFs, the figures should match those provided in the folder example_figures_SG_surveys.  The DOIs for the published article, and the title of the submitted article, are included in the first few lines of this script.

The script was written in MATLAB R2017a.
The script should use only base functions available in R2017a with the exception of suncycle.m which is available at: http://mooring.ucsd.edu/software/matlab/doc/toolbox/geo/suncycle.html.
suncycle.m is used to determine whether chlorophyll samples are during day or night before averaging.  If suncycle.m is not available, you will need to find a different function to determine local sunrise and sunset on line 544, or modify lines 544-549 such that chlorophyll samples are considered regardless of whether they are during day or night.  If you choose to do the latter, the figure based on these samples will not exactly match the provided example figure, fig_1_surveys_III_recreate.pdf, though it will be very similar.

To use this script, do the following:
1) Clone or download the script OSP_SG_surveys_bin_data_load_and_plot.m from this repository.
2) Download the files
  SG_at_osp_bin_avg_data.nc
  SG_at_osp_DAC_data.nc
  Pelland_et_al_SG_Surveys_III_Winkler_O2_Samples_at_OSP_2008_09.csv
  from the UW ResearchWorks archive (http://hdl.handle.net/1773/41656).
3) Change lines 20 and 23 of your version of OSP_SG_surveys_bin_data_load_and_plot.m to reflect the directories on your machine where the above three files are located.
4) Run your version of OSP_SG_surveys_bin_data_load_and_plot.m.

Note that the script was written to be run in cell mode -- that is, to run each cell of code sequentially.  Cells of code are delimited by double-percent signs (%%).  In MATLAB, the current cell is the cell in which your cursor is placed in the editor window.  To run that cell, select "Run Section" or "Run and Advance" in the editor window.  The latter will execute the code in the current cell and move the cursor to the top of the next cell.  Start with the first two cells which define the directories and load the data.

If you choose not to use cell mode, remove or comment out the "close all" statements at the beginning of each cell, because otherwise the first five figures will be closed before the script finishes executing, and only the final figure will be shown on screen.  In the initial commit, these statements are on lines 88, 159, 262, 357, 405, and 511.
