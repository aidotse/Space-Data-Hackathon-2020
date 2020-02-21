# Space-Data-Hackathon-2020

Introduction
The availability of large amounts of satellite imagery data through the European Copernicus project
and open source platforms like the OpenDataCube (ODC) greatly bolsters the opportunities to apply
classical machine learning and deep learning algorithms. These models can be employed to meet many
challenges. One challenge often arising in the analysis of satellite data is that of cloud occlusion.
Depending on the time of the year and the location of the Area of Interest (AoI) clouds can fully or
partially cover the image and hamper the analysis. There are, however, many methods available for
the estimation of missing data. The task in this challenge is to use the satellite data of Sweden
(provided through ODC) to train a model that is able to estimate certain statistics for an occluded area
based on the information from the surrounding area, as reliably and accurately as possible.
Background
One popular use of Earth observation imagery is the estimation of healthy vegetation in an area to
monitor events such as deforestation and droughts. Several vegetation indices have been created
along the years for this end. The Normalized Difference Vegetation Index (NDVI) we use here is one of
the most well known and widely applied version of these indices. It is calculated from the difference
of the surface’s absorption of visible red light (Red), and Near InfraRed light (NIR). While healthy
vegetation absorbs a large portion of light; it reflects back most of the infrared light. This is not the
case for vegetation that is unhealthy or sparse. Formally, the index is calculated as follows:
𝑁𝐷𝑉𝐼 =
𝑁𝐼𝑅−𝑅𝑒𝑑
𝑁𝐼𝑅+𝑅𝑒𝑑
The resulting value is between minus one and one, where values below 0.1 indicate barren areas of
rock, sand or snow; moderate values (0.2 to 0.3) indicate shrubs and grasslands; and high values (above
0.6) indicate the presence of dense and healthy vegetation (such as rain forests).
Goal
The challenge has a two-fold task.
1) The first part is a simple time-series prediction. Trend plots of an aggregate value, like the mean
NDVI, are calculated for an Area of Interest for each available day in the series of satellite images,
except for days with cloud cover where the aggregate will be missing. The goal of the trained model
is to accurately predict the missing values.
2) For the second part, the goal of the trained model is to accurately predict the missing values for
each individual pixel in the Area of Interest that was obscured. This task is related to interpolation not
only in the time dimension, but also in x and y coordinates and may use information from on the
surrounding area as well as earlier/later values for the given area.
While for the tasks above it is enough to assume the obscured area is rectangular, as a bonus task to
give you opportunity to demonstrate excellence, we ask you to make the analysis work for arbitrary
shaped Areas of Interest (up to a few kilometers across).
Task Description and Data
Data to be used: satellite imagery data of Sweden that will be available to be queried through the
OpenDataCube environment.
Expected outcome and evaluation metric: predicted values for test data will be compared to ground
truth values (here, the occlusion is artificial) in terms of Root Mean Square Error (RMSE)
Requirements
• Experience with programming (Python)
• Basic knowledge of time-series prediction and image processing methods
• Familiarity with some Open Data Cube examples for querying and visualising data
(https://datacube-core.readthedocs.io/en/stable/user/guide.html)
References
https://www.harrisgeospatial.com/Learn/Whitepapers/WhitepaperDetail/ArtMID/17811/ArticleID/16162/Vegetation-Analysis-Using-Vegetation-Indices-in-ENVI
(Vegetation Analysis: Using Vegetation Indices in ENVI, u.d.)
https://earthobservatory.nasa.gov/features/MeasuringVegetation
(Measuring Vegetation, u.d.)
