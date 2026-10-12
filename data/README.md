# Data

This directory stores all datasets used in the project.

## raw/

Contains the original downloaded datasets.

These files should never be modified or overwritten.

### raw/nhdplus/

Contains NHDPlus V2 Great Lakes VPU 04 data.

Main datasets:

- `NHDSnapshotFGDB/`
  - contains `NHDFlowline`
  - stream/river geometry

- `NHDPlusCatchment/`
  - contains catchment polygons associated with COMIDs

- `NHDPlusAttributes/`
  - contains `PlusFlow`
  - contains `PlusFlowlineVAA`
  - used for graph connectivity and reach attributes

- `VPUAttributeExtension/`
  - additional NHDPlus attributes

### raw/nlcd/

Contains Annual NLCD land-cover rasters from 1985–2025.

Example:

- `Annual_NLCD_LndCov_1985-1994_CU_C1V2/`
- `Annual_NLCD_LndCov_1995-2004_CU_C1V2/`
- `Annual_NLCD_LndCov_2005-2014_CU_C1V2/`
- `Annual_NLCD_LndCov_2015-2024_CU_C1V2/`
- `Annual_NLCD_LndCov_2025_CU_C1V2/`

These rasters will later be used to calculate land-cover fractions for each NHDPlus catchment.

### raw/npdes/

Contains EPA ECHO ICIS-NPDES discharge/outfall data.

Main data:

- NPDES discharge points
- facility and outfall coordinates
- permit information
- design flow
- pollutant information

### raw/water_quality/

Contains observed water-quality datasets.

This folder can remain empty until a water-quality dataset is selected.

---

## interim/

Contains intermediate outputs created during processing.

Examples:

- cleaned NHDPlus node tables
- temporary graph tables
- yearly NLCD catchment statistics
- NPDES-to-COMID matching results

These files can be regenerated from the raw data.

---

## processed/

Contains final model-ready datasets.

Expected outputs include:

- `nodes_static.parquet`
- `nodes_yearly.parquet`
- `edges.parquet`
- `catchments.gpkg`

These files will be used directly for graph construction and modeling.