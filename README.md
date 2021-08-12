# BCET
BCET for WorldView3 Imagery
This repository contains the follwoing files:
1. Most up to date .ipyth BCET code
2. WV3 MUL bands .tif (as given, no orthorecitifcation or processing) (1.58 GB)
3. WV3 SWIR bands .tif (as given, no orthorecitifcation or processing) (170.07 mb)
4. WV3 PAN band .tif (as given, no orthorecitifcation or processing) (3.16 GB)

Notes:
1. The spatial extent of the WV3 imagery is contained in one scene (tile) and is georeferenced to WGS 1984 UTM Zone 19S. The spectral extent is contained in three images (8 MUL bands, 8 SWIR bands, 1 Panchromatic band). The radiometric resolution of the MUL and Pan bands is 11-bit, and 14-bit for the SWIR bands. They are all stored as 16-bit with unsigned integers. 
2. I need to contact Apollo Mapper to find out what product level of data we recieved/level of pre-processing (e.g. atmospheric correction?).
3. The WV3 imagery attached is the original data given to me (not orthorecitfied). With this imagery, 'nodata' values are given as "none". However, the imagery we have been working with thus far was the orhtorecitifed copy. Once upladed into ArcMap for orthorecitification, 'nodata' values became 0.0. If needed, this 'none' nodata value can be changed in ArcMap without orthorecifying the images. The processes is to use the 'Clip' tool to clip raster to itself and set "No Data" value to whatever you want when promted.  
4. The BCET seems to work okay when using a smaller clipped version of the image. However, It fails with the full scene. This may be because a larger range of values need to be accomidated for, but it could also be due to introducing more noise. We can try to clip the full scene histograms to 1% and 99% in python to see if it makes a difference. The BCET algorithm directly uses the min() and max() values of each layer as the input coefficients, so outlier/noise values will have a large influence on the calculation. 
