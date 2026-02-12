# 2024_SWPA_UOGD_Impact

This repository contains materials affiliated with the article entitled **"Targeted Sampling Reveals Localized Brine Signals Amidst Otherwise Unimpacted Water Quality Near Unconventional Oil and Gas Development"**, submitted to *Water Research*. 

# Project Summary

This project re-evaluates the impact of Unconventional Oil and Gas Development (UOGD) on groundwater quality within the Marcellus Shale region of southwestern Pennsylvania, addressing persistent concerns regarding potential contamination. While prior studies analyzing data from 2008 to 2018 suggested regional associations between drilling activity and elevated salinity, our 2024 investigation sought to determine if these patterns persist under current conditions. We collected and analyzed 97 water samples from private wells, springs, and streams, utilizing a targeted sampling strategy that focused on previously identified chloride hotspots, decommissioned wastewater impoundments, and recent spill sites, alongside appropriate control locations. We evaluated water quality against health-based standards, tested the differences between samples near above mentioned sites and controls, while accounting for complex geologic and topographic variables using fixed effect modeling and watershed delineation. 

Our findings indicate that widespread, regional groundwater degradation attributable to UOGD is not evident in the recent data. Impacts appear to be rare and highly localized rather than systemic; for instance, among five spill sites we further investigated, only one groundwater sample exhibited elevated salinity and brine-associated markers. Geochemical and isotopic analysis suggests this specific anomaly resulted from localized influence via deeper groundwater flow paths rather than surface transport. We also emphasized the importance of combining broad regional screening and targeted, hydrogeology-informed monitoring to assess potential UOGD-related groundwater contamination.

# Data
All datasets used in this study are available in the `Dataset` folder.

| File | Description |
|------|-------------|
| `2024_swpa_dataset.csv` | Complete dataset containing sampling information and water chemistry data for all 97 samples collected in this study. For privacy concerns, private well owner information is not disclosed and coordinates are truncated to two decimal places. |
| `Full_Table_Data_for_stats.csv` | Processed subset of `2024_swpa_dataset.csv` containing water chemistry data for 90 groundwater samples used in statistical analyses. Concentrations below detection limits were assigned their respective detection limit values. |
| `Full_Table_Units.csv` | Measurement units for all water chemistry analytes. |
| `df_fixed_effect.csv` | Subset of `2024_swpa_dataset.csv` used for fixed-effect modeling. |
| `EPA_Standard_with_health_risk.csv` | EPA drinking water standards ([MCL](https://www.epa.gov/ground-water-and-drinking-water/national-primary-drinking-water-regulations) & [SMCL](https://www.epa.gov/sdwa/secondary-drinking-water-standards-guidance-nuisance-chemicals)) and other health-related thresholds. |
| `Isotech_data.csv` | Gas geochemistry data for samples analyzed in this study. |
| `PADEP_data.csv` | Water samples collected as part of the Water Quality Monitoring Plan during Spill A remediation. Data obtained through a Freedom of Information Act (FOIA) request to the Pennsylvania Department of Environmental Protection (PADEP). Additional details are available in the supplementary information.|
| `Global_Gas_Geochemistry_Inventory_2017.csv` | Global gas geochemistry data from [Owen et al. (2017)](https://doi.org/10.5194/essd-9-639-2017). |
| `shale_network_washington.csv` | Subset of the Shale Network database ([available here](https://doi.org/10.26208/DT5Y-5B37)) containing groundwater samples collected in Washington County. |
| `USGS_produced_water_data_2023.xlsx` | USGS National Produced Water Geochemical Database v3.0 from [Blondes et al. (2023)](https://doi.org/10.5066/P9DSRCZJ). |


# Analysis

All scripts used for statistical and geospatial analysis are included in `Scripts` folder. All outputs from these scripts will be saved in the `Results` folder. 

| File | Description | Output |
|------|-------------|--------|
| `Stats_Summaries_WMW_BM_Tests.ipynb` | Generates statistical summaries of the 90 groundwater samples and their subgroups (HS, I, S, and C) to examine exceedances of water quality standards; performs regression analysis of brine-related species against distances to nearest unconventional oil and gas wells, impoundments, and spills to assess regional trends; conducts one-sided Wilcoxon–Mann–Whitney (WMW) and Brunner–Munzel (BM) tests with Benjamini–Hochberg corrections between HS, I, S, and C groups, and between samples in ridge and valley settings. | Tables 3, S2–S10 |
| `fixed_effect_model_spill_investigation.ipynb` | Performs fixed-effect modeling to examine correlations between brine-related species and proximity to infrastructure sites while accounting for potential confounding factors (e.g., road salting). Also includes detailed investigation of five spills, comparing spill samples from this study with nearby Shale Network and PADEP samples. | Tables 4, S11–S17 |
| `Figure_2A_gas_geochem.ipynb` | Plots methane (C₁) versus ethane (C₂) + propane (C₃) concentrations against δ¹³C–CH₄ for groundwater samples. | Figure 2(A) |
| `Figure_2B_Sr_isotope.ipynb` | Plots ⁸⁷Sr/⁸⁶Sr as a function of [Sr]/[Cl] (mg/L) for groundwater samples. | Figure 2(B) |
| `Figure_2C_2D_Cl_Br_ratio.ipynb` | Plots Cl/Br mass ratios across HS, I, S, and C samples, with comparison to produced water samples. | Figures 2(C), 2(D) |


# Figures & Tables

Figures and tables from the main text and SI showing the results of our analyses are already stored in the `Results/Figures` and `Results/Tables` folder, respectively.


# Requirements

**Python**
- Version 3.13.12 or higher
- Dependencies are included in `python_requirements.txt`

**R**
- Version 4.4.2 or higher
- Dependencies are included in `r_requirements.csv`

# Contacts

For questions, please reach out to Jianfeng Su at jsu124@syr.edu or Dr. Tao Wen at twen08@syr.edu.

# Acknowledgements

This material is based on work supported by the Health Effects Institute (grant number 143815 to Jennifer Baka, Pennsylvania State University, with subcontract to Tao Wen at Syracuse University). Author would also like to acknowledge support from the National Science Foundation (grant number OAC-2209864).




