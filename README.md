# Mapping a Sustainable Water Future: Private Sector Opportunities for Global Water Security and Resilience (code to support GEC 2024 publication)

<font color=red>Title: Mapping a Sustainable Water Future: Private Sector Opportunities for Global Water Security and Resilience (code to support GEC 2024 publication)
Author: Pamela Green  
Date: August 17, 2024  

This code was developed between October 2021 and August 2024 by Pamela Green and includes the development and creation of all raster and tabular data included in the manuscript with same title.  </font>

The following data were downloaded, processed,and assembled during the project period. All input datasets are resampled from their native formats to 6-minute resolution GeoTIFF raster format using a standard reprojection and warping utility (GDAL Warp).

<b>Water Threats</b>

Water threat indicators from Vörösmarty et al 2010 (available from https://riverthreat.net/data.html), noted below, are resampled to 6-minute grid cell resolution using a nearest-neighbor algorithm.

| Vörösmarty et al 2010 dataset | Acronym
| --- | --- |
| Incident Human Water Security Threat | HWS
| Adjusted Human Water Security Threat | aHWS
| Investment Benefit Factor | IBF
| Water Resource Development Threat Theme | WRD
| Pollution Threat Theme | PO
| Catchment Disturbance Threat Theme | CD
| Biotic Factor Threat Theme | BF


<b>Contemporary Climate Variability</b>

Contemporary Climate Variability indicator is developed by calculating the intra- and inter annual variability in available water resources from CUNY WBM water balance model monthly and annual river discharge outputs using the TerraClimate high resolution data set of monthly climate forcings (Abatzoglou, et al. 2018, Wisser et al. 2010) at 6-minute grid cell resolution for the period 2000-2020. Coefficient of Variation (CV) indicators are calculated across the time periods specified as (Standard Deviation / Mean). The CV indicators are then ranked with a cumulative dstribution function (CDF) on a continuous 0-1 scale of low to high climate variability threat using the rankCDF function in this Notebook this identifying areas most vulnerable to large shifts in water availability due to seasonality (intra-annual) and longer term (30-year inter-annual) climate patterns. 
 
Existing Juypter Notebook code was used to create the Climate Variability CDF data which is directly imported into this code from the Model_Input/WBM/WBM_TerraClimate2000-2020_Q_DIST_CDF_InterIntra_6min.tif. Seperate rasters for the intra- and inter- annual Climate Variability CDFs are included for completeness. 

<b><i>Enabling Environment Indicators</i></b>

 
<b>Global Innovation Index Data</b>

Global Innovation Index country score data for 2023 was downloaded from https://tind.wipo.int/record/46596. Scores were linearly rescaled and converted to a fraction (divide by 100) so the maximum score was 1.0. Countries that were excluded from the 2023 GII listing due to insufficient data but assigned a score in a previous year were assigned a GII score associated with the same ranked position for that country from the most recent year of record. Countries omitted from the GII analysis were assigned the adjusted GII value associated with the lowest ranking score for each omitted country’s UN designated regional cohort.The GII tabular data is linked to the GADM country boundaries for spatial processing.

<b>SDG 6.5.1 IWRM</b>

The SDG 6.5.1 IWRM implementation indicator was downloaded from the IWRM data portal at http://iwrmdataportal.unepdhi.org/. Scores were linearly rescaled and converted to a fraction (divide by 100).The IWRM data is linked to the GADM country boundaries for spatial processing.

<b>Adaptive Capacity Index Data</b>

The Adaptive Capacity Indicator data was downloaded from the DataDryad open repository at https://datadryad.org/stash/dataset/doi:10.5061/dryad.h2v2398. Scores were linearly rescaled and converted to a fraction (divide by 100).The IWRM data is linked to the GADM country boundaries for spatial processing.

<b>WIN and PrivateOI Indicators</b>

The contemporary Climate Variability indicator is applied to the HWS and threat theme indicators from Vörösmarty et al 2010 above to create the Water Investment Needs (WIN) indicators measuring the combined impacts of climate variability and water threats for contemporary conditions. The spatial GII indicator is applied to the WIN indicators to create the Private Opportunity (PrivateOI) indicators identifying the impacts of enabling environment state on private sector investment opportunties. WIN and PrivateOI indicators are ranked on a continuous 0-1 scale of low to high needs/opportunities using the rankCDF function in this Notebook.

<b>Casting Water WIN and PrivateOI in Terms of Water Resource Areas Supporting Downstream Populations</b>

We use the WIN and PrivateOI indicators described above to map population downstream of water source areas under varying levels of needs and opportunities. We map the geography of population downstream of water source areas under low, moderate, and high scores for each of the WSN and PrivateOI indicators under contemporary conditions. 

<b>Country Designations and Spatial Boundaries</b>

Country boundaries are derived from the GADM database (avaiable at https://gadm.org/data.html) and converted to raster format at 6-minute resolution for processing with raster water threat data. Smaller nations and island nations not present in the water threat raster dataset are not included from the GADM database. 

<b>Population Distribution</b>

Local Population for 2020 is from GPWv4 database (CIESIN 2018) and downloaded via https://sedac.ciesin.columbia.edu/data/set/gpw-v4-population-count-rev11. Downstream population is processed via a routing algorithms using the CUNY WBM RGIS system and the WBM flow data described above.

References:

Abatzoglou, J. T., Dobrowski, S. Z., Parks, S. A. & Hegewisch, K. C. TerraClimate, a high-resolution global dataset of monthly climate and climatic water balance from 1958–2015. Sci. Data 5, 170191 (2018).

Center for International Earth Science Information Network - CIESIN - Columbia University. 2018. Gridded Population of the World, Version 4 (GPWv4): Population Density, Revision 11. Palisades, NY: NASA Socioeconomic Data and Applications Center (SEDAC).

Dutta, S., Lanvin, B., Wunsch-Vincent, S., León, L. R. & World Intellectual Property Organization. Global innovation index 2022. doi:10.34667/TIND.46596

GADM. GADM database of Global Administrative Areas. https://gadm.org/data.html (2016).

Vorosmarty, C.J.,  P.B. McIntyre, M.O. Gessner, D. Dudgeon, A. Prusevich, P. Green, S. Glidden, S.E. Bunn, C.A. Sullivan, C. Reidy Liermann, and P.M. Davies. Nature 467, 555-561 (30 September 2010) doi:10.1038/nature09440.

Wisser, D., B. M. Fekete, C. J. Vörösmarty, and A. H. Schumann. “Reconstructing 20th Century Global Hydrography: A Contribution to the Global Terrestrial Network- Hydrology (GTN-H).” Hydrology and Earth System Sciences 14, no. 1 (January 6, 2010): 1–24. https://doi.org/10.5194/hess-14-1-2010.

```markdown
Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
```

Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

