# Airborne-Laser-Scanning
For all things CRREL ALS

This is a repo for developing ALS post-processing code as well as tracking system documentation, functionality, development, and bugs. We will start with ALS post-processing code and eventually work the system stuff in. 

Table of contents:

00_combine-and-tile - This is the command for reading in the flight line records and prodcuce n-unit by n-unit tiles.

01_clean-and-classify.json - This pipeline first cleans the point clouds by applying filters.dem, then further eliminates noise points with filters.outlier and then finally classifies the points using the simple morphological filter (filters.smrf). The input to this pipeline is a directory of raw las/laz files. The output is a directory of cleaned and classified las/laz files.

02_adjust-to-control.json - This pipeline adjusts the points to control by applying a transformation matrix (filters.transformation) that is determined using the QTM point utility tool. We will eventually update this step using automated methods. The input to this pipeline is a directory of cleaned and classified las/laz files. The output is a directory of cleaned, classified, and adjusted las/laz files.

03A_extract-dem.json - This pipeline writes a bare earth DEM for each input record. The input to this pipeline is a direcory of classified las/laz files. The output is a directory of GeoTiff files.

03B_output-ground-points.json - This pipeline writes a bear earth DEM for rach input record as well as writing a bare earth las/laz file for each input record. This pipeline replaces 3A if and only if the customer explicitly requests ground point las/laz files. Otherwise this is not run. The input is a directory of classified las/laz files. The output is a directory of las/laz files and a directory of GeoTiff files. 

04_combine-tile-dems.txt - This is the command to merge the n-unit by n-unit tiles into a single DEM.

ALS-Processing_Notebook.ipynb - A juypter notebook built by Shad O'Neel to execute the processing workflow.

workflow-diagram-8_27_2021.drawio - The draw.io file for the most up-to-date workflow diagram. This file *should* be able to be edited in draw.io (diagrams.net) directly from this repo.

workflow-diagram-8_27_2021.svg - The svg file for the most up-to-date workflow diagram. This image is embedded in the ALS Processing Workflow Wiki page. 
