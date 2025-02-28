## Tools for undertaking the Red List of Ecosystems Assessment (terrestrial)

### **National Biodiversity Assessment - South Africa**

*South African National Biodiversity Institute (SANBI)*

February 2025

#### Summary

*This Repository contains the following workflows that together result in the 2025 Red List of Ecosystems for Terrestrial Ecosystems of South Africa.*

1.  Calculate Criterion A3 national land cover data [RLE2024_A3.qmd](RLE2024_A3.qmd);

2.  Calculate Criterion A2b and B1i and B2i using national land cover data [RLE2024_A2b.qmd](RLE2024_A2b.qmd)

3.  Calculate Criterion B1iii & B2iii using ongoing decline based on Red List of Threatened Species - pressures from fires, overgrazing and invasive plants (SANBI 2024) [RLE2024_B_species.qmd](RLE2024_B_species.qmd)

4.  Collate all assessments for all criteria [RLE_compilation.qmd](RLE_compilation.qmd) using the three assessments above plus :

-   Criterion A3 assessments using Western Cape (Cape Nature), KwaZulu-Natal (EKZN), Mpumalanga data (MPTA). Workflow in the LCC_terr repo [WC_KZN_MPL_LC.qmd](WC_KZN_MPL_LC.qmd)

-   Criterion A3, B1, B2, and D3 assessments using City of Cape Town BioNet data (CoCT, 2024) . Workflow in the LCC_terr repo [CoCT_LC_Condition.qmd](CoCT_LC_Condition.qmd)

-   Criterion B assessments using the National Invasive Alien Plant Survey (Kotze et al., 2024) . Workflow in the INV_terr repo [Invasives_niaps.qmd](Invasives_niaps.qmd)

-   Criterion B assessments using CFR Invasive Alien Tree Survey (Rebelo et al. 2024) . Workflow in the INV_terr repo[Invasives_rebelo_wc.qmd](Invasives_rebelo_wc.qmd)

-   Criterion D assessments using STEP data (Lloyd et al., 2022) . Workflow in the LCC_terr repo [STEP_Condition.qmd](STEP_Condition.qmd)

-   Criterion D assessments using Little Karoo data (Thompson et al., 2009). Workflow in the LCC_terr repo [LittleKaroo_Condition.qmd](LittleKaroo_Condition.qmd)

-   Criterion D assessments using Nelson Mandel Bay Metro data. Workflow in the LCC_terr repo [NMB_Condition.qmd](NMB_Condition.qmd)

#### Calculating metrics of ecosystem extent and assessing RLE Criteria A3

R tidy script ([RLE2024_A3.qmd](RLE2024_A3qmd)) in Quarto format showing how [land cover change metrics](askowno/LCC_terr/ouputs/lc7_rall.csv) from the Land Cover Change workflow ([LCC_terr](askowno/LCC_terr/LC_change_7class_veg24.qmd)) were ingested and summarised, and then used in assessment of RLE Criterion A3.

For Criterion A3 the key metric is the ecosystem extent remaining in natural condition at each time point expressed as a proportion of the historical / potential extent of the ecosystem type (e.g. extent2022/ext1750). This is used to assess Criterion A3 for each ecosystem type. The results are captured in wide ([outputs/results_A3w.csv](outputs/results_A3w.csv)) and long ([outputs/results_A3.csv](outputs/results_A3.csv)) formats.

#### Calculating rate of decline in ecosystem extent and assessing RLE Criteria A2b and then using this in Criterion B

R tidy script ([RLE2024_A2b.qmd](RLE2024_A2b.qmd)) in Quarto format showing how [land cover change metrics](askowno/LCC_terr/ouputs/lc7_rall.csv) from the Land Cover Change workflow ([LCC_terr](askowno/LCC_terr/LC_change_7class_veg24.qmd)) were ingested and summarised, and then used in assessment of RLE Criterion A2b.

For Criterion A2b the key metrics relate to the rate of habitat loss (decline in ecosystem extent), and the use of these to project ecosystem extent forward to 2040, and then assess the proportion of 1990 extent that will be lost over a 50 year period to 2040. This information is used to assess Criterion A2b for each ecosystem type. The results are captured in wide ([outputs/results_A2b.csv](outputs/results_A2b.csv)) format.

1.  Compute the absolute rate of decline in ecosystem extent (ARD) over the period 1990 to 2022, the period 1990-2014, 2014-2022 and 2018-2022 (to provide recent trend).
2.  This ARD can be used to estimate ecosystem extent in 2040 to allow for computation of Criterion A2b (recent and ongoing declines). The simplest approach is to calculate the rate of decline in natural extent per year and then multiply by 50 to get the projected extent in 2040 (i.e. ext2040 = ARD9022 / 32 \* 50 ).
3.  Then subtract this from the 1990 extent and divide by the 1990 ext to get the proportional decline in extent over a 50 year period (i.e. proportion lost over 50 years = (ext1990 - ext2040/ext1990) .
4.  In addition to this we projected the 2040 extent using ARD for 1990-2014 (previous), for 2014-2022, for 2018-2022 (to provide recent trends).
5.  To complement these simple calculations we included three models of decline i) linear, ii) quadratic and iii) a monotonic spline.
6.  RoD (%/y) is an additional metric (i.e. R0D9022 = ARD9022/32) used in Criterion B as evidence of ongoing decline (if the ROD \>= 0.4%/y), for the revised assessment the ROD for three periods was calculated to allow assessor to gauge the level of ongoing threat that habitat loss presents (i.e. RoD9022, RoD9014, RoD1422 and RoD1822 were calculated).

#### Add info for other workflows...
