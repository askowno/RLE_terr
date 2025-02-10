## Tools for undertaking the Red List of Ecosystems Assessment (terrestrial)

### **National Biodiversity Assessment - South Africa**

*South African National Biodiversity Institute (SANBI)*

February 2025

1)  R terra and sf script in a Quarto document ([RLE2024_B1.qmd](RLE2024_B1.qmd)) to calculate EOO for vegetation remnants layer - thus avoiding limitations of redlistr package which struggled to calculate EOO for a remnants raster at less than 120m pixel resolution (at 120m some small ecosystem features can be lost in rasterize process). EOO is required for RLE Criterion B assessments. The [output](outputs/results_df_B1_EOO.csv) is a table of EOO (km2) per ecosystem / vegetation type. The code can be applied to any ecosystem input data and will work well for wetlands and other small ecosystems with small features.

2)  R tidy scripts within a Quarto document ([RLE2024_A2b_A3.qmd](RLE2024_A2b_A3.qmd)) which ingest [land cover change metrics](askowno/LCC_terr/ouputs/lc7_rall.csv) from the Land Cover Change workflow ([LCC_terr](askowno/LCC_terr/LC_change_7class_veg24.qmd)) for RLE Criterion A2b and A3 assessments. The [output](outputs/results_df_A2b_a3.csv) table (long format to handle time series) has various metrics for each vegetation type at each time point, including: proportion natural remaining habitat, rate of habitat loss between various periods, absolute rate of decline etc. and the Red List category for which the type qualifies.
