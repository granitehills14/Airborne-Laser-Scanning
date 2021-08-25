# Airborne-Laser-Scanning
For all things CRREL ALS

This is a repo for developing ALS post-processing code as well as tracking system documentation, functionality, development, and bugs. We will start with ALS post-processing code and eventually work the system stuff in. 

Table of contents:

als-cleaning.json - cleans the point clouds using the dem filter and the outliers filter, classifies the point cloud using the smrf filter, and writes new laz files.

adjust-and-extract-ground.json - applies a transformation matrix to the point clouds to adjust them to control (matrix is determined manually in QT), classifies the point cloud using the smrf filter (probably redundent), writes laz files of all points, writes laz files of just the ground points (needed?), and then extracts and writes a bare earth DEM as a geotiff.

learn_python_pdal.ipynb - a juypter notebook built by Shad O'Neel to execute the processing workflow. 
