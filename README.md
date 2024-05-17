# climate-variability
Climate variability refers to variations in the climate system that occur over a range of time scales, from months to decades, and sometimes longer. These variations can be natural or influenced by human activities.
This was assigned to us to assess the climate variability for North-East Region.
The Question.
The North-East Region Lead by their regional minister wants to seeks funds from the climate change and impact fund from the government. Because of this the Regional director for North East Municipal assembly has call on you to provide some basic information to help them Draft the proposal. You are to determine the Normalized Difference vegetation index (NDVI) for 2003 and 2021. You are also to determine the land surface Temperature (LST) for the two years and perform some regression analysis using the NDVI, Temperature and Rainfall. The correlation between these Variables will be necessary for documentation. 
Materials 
1.	Landsat image for 2003 and 2021 
2.	Rainfall data from CHIRPS
3.	Shapefile of North East Region
4.	Sample points 
For this exercise, consider the following steps:
1.	Perform radiometric correction on the Landsat images (Hint: check both ‘apply DOS’ and ‘Brightness Temperature (BT)’
BT = 1321.08 / Ln (774.89/” Band10Radiance + 1) – 272.15
2.	Clip the corrected images with the North East shapefile 
3.	Calculate the NDVI for the images 
4.	Using Raster Calculator calculate proportion of vegetation
  

PV is defined as the ratio of the vertical projection area of vegetation (containing leaves, stalks, and branches) on the ground to the total vegetation area.

5.	Then calculate Land Surface Emissivity (LSE) using this formula 
Emissivity refers to the ratio of the radiated energy from the surface of an object to that energy radiated from a perfect emitter, known as a blackbody, at the same temperature and wavelength and under the same viewing conditions.
6.	Using the PV and LSE calculate the Land surface Temperature (LST) using the formula  
TB is the brightness temperature, λ is the central band wavelength of emitted radiance,   (approximately = 1.438 x 10-2 mK), where σ is the Boltzmann constant, h is the Planck's constant, and c is the velocity of light.
λ for   LE07_Band 6_1 = 10.40 µm
	LE07_Band 6_2= 10.40 µm
	LC08_Band 10= 10.3 µm
LC08_Band 11= 11.5 µm
Land surface temperature (LST) is the radiative skin temperature of the land derived from solar radiation. LST measures the emission of thermal radiance from the land surface where the incoming solar energy interacts with and heats the ground.

7.	Using the sample points Extract the Values of NDVI, LST and rainfall for the point (use the Sample Raster values in the processing tool)
8.	Save the sample point in csv format. Using Excel perform a simple linear regression for ‘NDVI-LST’, NDVI-Rainfall and LST-Rainfall.

   Procedure 
   I used QGIS for this assignment.
   QGIS (Quantum Geographic Information System) is an open-source geographic information system (GIS) application that allows users to create, edit, visualize, analyze, and publish geospatial information. It supports various vector, raster, and database formats and functionalities.
   To assist the North East Regional Minister in drafting a proposal for seeking funds from the climate change and impact fund, I went through a detailed procedure using QGIS to analyze the Normalized Difference Vegetation Index (NDVI) and Land Surface Temperature (LST) for the years 2003 and 2021. I also perform a regression analysis using NDVI, temperature, and rainfall data in excel. Here's a step-by-step guide:


 1. Radiometric Correction

1. Open QGIS and load the Landsat images for 2003 and 2021.
2. Apply DOS Correction:
   - Use the Semi-Automatic Classification Plugin (SCP) to perform atmospheric correction.
   - Go to SCP > Preprocessing > Landsat > DOS1.
3. Brightness Temperature (BT) Calculation:
   - Calculate the BT using the formula:
    (formula was given in the question)
   - Use the Raster Calculator to apply this formula on Band 10 (for Landsat 8) or the appropriate band for other Landsat versions.

 2. Clip Images with North East Shapefile

1. Load the North East Region shapefile.
2. Use the Clip Raster by Mask Layer tool:
   - Raster > Extraction > Clip Raster by Mask Layer.
   - Select the Landsat image as the input layer and the shapefile as the mask layer.
   - Ensure the clipped images are saved for both 2003 and 2021.

 3. Calculate NDVI

1. NDVI Calculation:
   - NDVI = (NIR - Red) / (NIR + Red).
   - Use Raster Calculator:
     - For Landsat 8: NDVI = (Band 5 - Band 4) / (Band 5 + Band 4).
     - For earlier Landsat: adjust bands accordingly (e.g., Landsat 7: Band 4 - Band 3 / Band 4 + Band 3).
   - Save the resulting NDVI images for both years.

 4. Calculate Proportion of Vegetation (PV)

1. Proportion of Vegetation (PV):
   - Define thresholds to classify vegetation.
   - Use the Raster Calculator to create a binary raster indicating vegetation presence.
   - PV can be derived by calculating the area covered by vegetation in relation to the total area.

 5. Calculate Land Surface Emissivity (LSE)

1. Land Surface Emissivity (LSE):
   - Use the formula:
    
      (formula was given in the question)
   - Apply this formula in the Raster Calculator.

 6. Calculate Land Surface Temperature (LST)

1. LST Calculation:
   -use the formula:
      (formula and constants was given in the question)
     
   - Apply this formula in the Raster Calculator to obtain the LST for both years.

 7. Extract Values at Sample Points

1. Sample Points Extraction:
   - Load the sample points shapefile.
   - Use the **Point Sampling Tool**:
     - Vector > Research Tools > Point Sampling Tool.
     - Select the NDVI, LST, and rainfall rasters as layers to sample.
     - Save the sampled values to a CSV file.

 8. Perform Regression Analysis

1. Load CSV in Excel:
   - Import the CSV file with sampled values into Excel.
2. Regression Analysis:
   - Use Excel’s Data Analysis Toolpak to perform regression:
     - Analyze NDVI-LST, NDVI-Rainfall, and LST-Rainfall relationships.
   - Calculate the correlation coefficients and document the relationships.

 Observations

1. NDVI:
   - Compare NDVI values between 2003 and 2021 to assess vegetation health and changes.
   - Higher NDVI values typically indicate healthier and denser vegetation.

2. LST:
   - Analyze LST changes to understand surface temperature variations over the years.
   - Higher LST values may indicate urbanization or deforestation.

3. Rainfall:
   - Correlate rainfall data with NDVI and LST to understand the impact of precipitation on vegetation and temperature.

4. Regression Analysis:
   - Examine the strength and direction of relationships:
     - Positive correlation between NDVI and rainfall might indicate vegetation growth with more precipitation.
     - Negative correlation between NDVI and LST might suggest that higher temperatures reduce vegetation health.
     - Correlation between LST and rainfall will help understand how precipitation influences surface temperatures.

 Conclusion

Using QGIS and Excel, the analysis provides a comprehensive view of how climate variability impacts vegetation and surface temperatures in the North East Region. This information is crucial for drafting the proposal to seek funds, highlighting the need for climate adaptation and mitigation strategies.
