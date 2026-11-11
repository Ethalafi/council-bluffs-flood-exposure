# GIS Methodology: Council Bluffs Flood Exposure Analysis

## 1. Project Objective

Determine the percentage of Council Bluffs, Iowa, that falls within FEMA-designated Special Flood Hazard Areas (SFHAs) using publicly available geographic datasets and QGIS.

## 2. Data Sources

**FEMA National Flood Hazard Layer (NFHL)**
- Geographic coverage: Pottawattamie County, Iowa
- Source dataset: NFHL_19155C
- Effective study date: April 16, 2013
- Feature class: S_FLD_HAZ_AR

**U.S. Census Bureau**
- Dataset: 2024 Cartographic Boundary Files — Iowa Places
- Selected municipality: Council Bluffs, Iowa

## 3. Software and Coordinate Reference System

- GIS software: QGIS 4.2.2
- Project CRS: EPSG:26976 — NAD83 / Iowa South
- Primary data format: GeoPackage (.gpkg)

## 4. Data Preparation

The Council Bluffs municipal boundary was extracted from the U.S. Census Bureau's Iowa Places dataset and exported as a separate GeoPackage.

FEMA flood-hazard polygons were imported from the Pottawattamie County NFHL geodatabase.

During the initial clipping operation, QGIS identified invalid geometry in the FEMA dataset. The Fix Geometries tool was used to create a repaired copy of the flood-hazard polygons.

The repaired dataset was then clipped to the Council Bluffs municipal boundary.

## 5. Special Flood Hazard Area Selection

The clipped FEMA dataset contained 164 polygon features.

The `SFHA_TF` attribute was used to identify Special Flood Hazard Areas with the expression:

`"SFHA_TF" = 'T'`

This selection returned 53 polygon features, which were exported as a separate SFHA GeoPackage.

## 6. Spatial Processing

The 53 selected SFHA polygons were processed using the QGIS Dissolve tool without specifying a dissolve field.

This created a combined flood-hazard footprint while removing internal boundaries and avoiding double-counting overlapping areas.

## 7. Area Calculations

Areas were calculated in square miles using the QGIS expression:

`area($geometry) / 2589988.110336`

The dissolved SFHA footprint was calculated separately from the original polygon-area attributes.

The same calculation method was applied to the Council Bluffs municipal boundary.

## 8. Results

| Measurement | Result |
|---|---:|
| Council Bluffs municipal area | 45.4935 sq mi |
| Dissolved SFHA area | 10.4702 sq mi |
| Municipal area within SFHA | 23.01% |
| Selected SFHA polygons | 53 |

The percentage was calculated as:

`(10.4702 / 45.4935026) × 100 = 23.01%`

## 9. Cartographic Visualization

A professional map was created using QGIS Print Layout.

The map includes the Council Bluffs municipal boundary, dissolved SFHA footprint, legend, scale bar in miles, north arrow, key finding, and source attribution.

The final map was exported in PNG format at 300 DPI and as a PDF.

## 10. Limitations

This analysis measures the geographic extent of mapped SFHAs, not the number of people or structures exposed to flooding.

The FEMA source data represents regulatory flood-hazard mapping and may not reflect subsequent map revisions or all potential flooding scenarios.

The municipal boundary is derived from a generalized Census cartographic dataset, which may introduce spatial differences compared with more detailed local boundary data.

## 11. Potential Future Work

Additional analysis could incorporate building footprints, population data, transportation infrastructure, and critical facilities to estimate the potential impacts of flooding on developed areas.
