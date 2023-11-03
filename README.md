# MMapping Global Solutions for a Sustainable Water Future 

<font color=red>Title: <b>Mapping Global Solutions for a Sustainable Water Future/b>
  
  Author: DBPR 

This code was developed between October 2021 and November 2023 by Pamela Green and includes the development and creation of all raster and tabular data included in the manuscript with same title.  </font>
***

## Model Description

This code represents spatial modeling for development of a global mapping of Water Solution Needs (WSN) and Private Sector Opportunities Index (PrivateOI) in the water sector. WSN are defined by biogeophyscal, social and climate-driven pressures on water resources. PrivateOI are mapped as areas with high WIN and a regional capacity to attract and support private investments. The WSN and PrivateOI indices are spatially linked to populations who could benefit from improved investments in water security. The geographies of WSN and PrivateOI are compared across the globe and wealth spectrums, identifying locations where the private sector can best support water security at local, national, and regional scales.

A brief desciption of data inputs, model and outputs is listed below:

<b>Water Threats</b>

Water threat indicators from Vörösmarty et al 2010 (available from https://riverthreat.net/data.html), noted below, are used to define biogeophysical and societal threats to freshwater systems:

| Water Threat dataset | Acronym
| --- | --- |
| Incident Human Water Security Threat | HWS
| Adjusted Human Water Security Threat | aHWS
| Investment Benefit Factor | IBF
| Water Resource Development Threat Theme | WRD
| Pollution Threat Theme | PO
| Catchment Disturbance Threat Theme | CD
| Biotic Factor Threat Theme | BF


<b>Contemporary Climate Variability</b>

A Contemporary Climate Variability indicator is developed to defined pressures from climate change and uncertainty. Intra- and inter annual variability in available water resources is calculated from CUNY WBM water balance model monthly and annual river discharge outputs using the TerraClimate high resolution data set of monthly climate forcings (Abatzoglou, et al. 2018, Wisser et al. 2010). Coefficient of Variation (CV) indicators were calculated across the time periods specified as (Standard Deviation / Mean). The CV indicators were then ranked with a cumulative dstribution function (CDF) on a continuous 0-1 scale of low to high climate variability threat using the rankCDF function in this Notebook this identifying areas most vulnerable to large shifts in water availability due to seasonality (intra-annual) and longer term (30-year inter-annual) climate patterns. 
 
Existing Juypter Notebook code was used to create the Climate Variability CDF data which was  directly imported into this code from the Model_Input/WBM/WBM_TerraClimate2000-2020_Q_DIST_CDF_InterIntra_6min.tif. Seperate rasters for the intra- and inter- annual Climate Variability CDFs are included for completeness. 

<b>Enabling Environment Indicators</b>

<b>Global Innovation Index Data</b>

Global Innovation Index (GII) (Dutta et al 2022) is used as a proxy fro enabling environment supporting private sector investments. GII Country score data for 2022 was downloaded from https://tind.wipo.int/record/46596. Scores were linearly rescaled and converted to a fraction (divide by 100) so the maximum score was 1.0.  The GII tabular data is linked to a country boundary spatial dataset for spatial processing.

<b>Population Distribution</b>

Local Population for 2020 is from GPWv4 database (CIESIN 2018) and downloaded via https://sedac.ciesin.columbia.edu/data/set/gpw-v4-population-count-rev11. Downstream population was processed via a routing algorithms using the CUNY WBM RGIS system and the WBM flow data described above.

<b>WSN and PrivateOI Indicators</b>

The contemporary Climate Variability indicator is applied to the HWS and threat theme indicators from Vörösmarty et al 2010 above to create the WSN indicators measuring the combined impacts of climate variability and water threats for contemporary conditions. The spatial GII indicator is applied to the WSN indicators to create the PrivateOI indicators identifying the impacts of enabling environment state on private sector investment opportunties. WSN and PrivateOI indicators are ranked on a continuous 0-1 scale of low to high needs/opportunities using the rankCDF function in this Notebook.

<b>Casting Water WSN and PrivateOI in Terms of Water Resource Areas Supporting Downstream Populations</b>

We use the WSN and PrivateOI indicators described above to map population downstream of water source areas under varying levels of needs and opportunities. We map the geography of population downstream of water source areas under low, moderate, and high scores for each of the WIN and PrivateOI indicators under contemporary conditions. 


References:

Abatzoglou, J. T., Dobrowski, S. Z., Parks, S. A. & Hegewisch, K. C. TerraClimate, a high-resolution global dataset of monthly climate and climatic water balance from 1958–2015. Sci. Data 5, 170191 (2018).

Center for International Earth Science Information Network - CIESIN - Columbia University. 2018. Gridded Population of the World, Version 4 (GPWv4): Population Density, Revision 11. Palisades, NY: NASA Socioeconomic Data and Applications Center (SEDAC).

Dutta, S., Lanvin, B., Wunsch-Vincent, S., León, L. R. & World Intellectual Property Organization. Global innovation index 2022. doi:10.34667/TIND.46596

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

