# Spatio-Temporal Lagged Correlation Analysis Between Precipitation and Vegetation Dynamics - North Central Province, Sri Lanka (2010–2026)
## Overview

Understanding the relationship between rainfall variability and vegetation response is critical in semi-arid and irrigation-dependent regions such as the North Central Province (NCP) of Sri Lanka. Vegetation growth is strongly influenced by precipitation, but the response is often delayed due to soil moisture storage, irrigation practices, and ecosystem characteristics.

This project investigates the pixel-wise correlation between precipitation and NDVI, including lagged correlation analysis, to determine:
- How strongly vegetation responds to rainfall
- Whether vegetation response is immediate or delayed
- The spatial distribution of rainfall–vegetation coupling

The study was conducted over a custom Region of Interest (ROI) within North Central Province using multi-temporal satellite datasets from 2010 to 2026.

## Objectives
1. Compute monthly NDVI and precipitation composites
2. Analyze pixel-wise correlation between NDVI and rainfall
3. Perform lagged correlation (1–7 month lag)
4. Identify the optimal lag month for vegetation response

## Study Area
Custom ROI within North Central Province, Sri Lanka

This region is characterized by:
- Seasonal monsoonal rainfall
- Extensive irrigation networks
- Agricultural dominance (paddy cultivation)
- Dry zone climatic conditions

## Tools & Technologies
1. Google Earth Engine (GEE)
2. xee (Earth Engine → xarray integration)
3. geemap
4. xarray
5. NumPy
6. Matplotlib
7. Python

- Projection: EPSG:4326

## Datasets Used
1️. Precipitation Dataset
- Product: NASA GPM IMERG Monthly (V07)
- Source: NASA/GPM_L3/IMERG_MONTHLY_V07
- Band: precipitation
- Temporal resolution: Monthly

2️. Vegetation Dataset
- Product: MODIS MOD13Q1 (Version 6.1)
- Source: MODIS/061/MOD13Q1
- Band: NDVI
- Temporal resolution: 16-day (aggregated to monthly median)

## Study Period:
January 2010 – 2026

### Figure 1: Zero-Lag Correlation Map
<img width="563" height="432" alt="image" src="https://github.com/user-attachments/assets/82abd33c-cecc-4297-a21a-b90a424cbcec" />

- The zero-lag correlation map shows predominantly negative correlations (blue tones) across much of the study area. This indicates that vegetation greenness (NDVI) does not respond immediately to rainfall in the same month.

- In irrigated and reservoir-supported agricultural landscapes (common in the North Central Province), vegetation growth is often buffered by stored water rather than direct monthly rainfall. This explains the weak to negative same-month relationship.

### Figure 2: 3-Month Lag Correlation Map
<img width="563" height="432" alt="image" src="https://github.com/user-attachments/assets/f0cbaf8c-59a1-4193-9fea-04258e12d3e9" />

- The 3-month lag map shows a clear shift toward positive correlations (red tones) across large portions of the region.

- This suggests that vegetation responds to rainfall after a delay of approximately 2–4 months, which aligns with:
1. Soil moisture accumulation dynamics
2. Irrigation scheduling patterns
3. Crop growth cycles (especially paddy cultivation)

- The eastern portion still shows weaker or slightly negative correlations, possibly due to:
1. Different cropping calendars
2. Soil characteristics
3. Irrigation dependency
4. Land cover heterogeneity

### Figure 3: Multi-Lag Correlation (1–7 Months)
<img width="1180" height="590" alt="image" src="https://github.com/user-attachments/assets/7fda2dfb-6c5b-4caf-83a1-5ec327af47a6" />

The multi-lag panels (1–7 months) reveal a transition pattern:
- Lag 1–2 months: Mixed, weak relationships
- Lag 3–4 months: Stronger positive correlations dominate
- Lag 5–7 months: Correlations weaken again

This indicates that the optimal vegetation response window lies between 3–4 months after rainfall.

### Figure 4: Optimal Lag Map
<img width="558" height="438" alt="image" src="https://github.com/user-attachments/assets/0e79a0c3-af98-4767-be6a-ef5128a5b841" />

The optimal lag map (values 1–7) shows spatial variability:
1. Western and central parts → Mostly lag 3–4 months
2. Eastern and some peripheral areas → Lag 5–7 months
3. Some small pockets → Shorter lags (1–2 months)

This spatial heterogeneity reflects:
- Differences in irrigation access
- Soil water holding capacity
- Cropping intensity
- Microclimatic variation

## Notes
1. The North Central Province is dominated by tank-based irrigation systems, which likely explain delayed NDVI response.
2. The 3–4 month optimal lag aligns with major cropping cycles (Maha and Yala seasons).
3. Results can support:
- Drought early warning systems
- Crop yield forecasting
- Water allocation planning
- Climate adaptation strategies


## Limitations
1. Correlation ≠ Causation
- The analysis identifies statistical relationships but does not prove direct causality.

2. Monthly Aggregation
- Monthly composites may smooth short-term rainfall events and rapid vegetation responses.

3. NDVI Saturation Effect
- NDVI may saturate in dense vegetation, limiting sensitivity in certain areas.

4. Precipitation Data Resolution
- GPM IMERG resolution (~0.1°) may not capture fine-scale rainfall variability.

5. Land Cover Mixing
- Different land cover types (forest, agriculture, water bodies) are analyzed together unless masked separately.

6. No Irrigation Dataset Included
- Irrigation water availability was not explicitly modeled, though it strongly influences vegetation dynamics in the region.

