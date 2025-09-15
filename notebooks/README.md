# Regional SST Subset (Module 2 Check-In)

This repository includes a small NetCDF file, `regional_sst_subset.nc`, created from NOAA OISST v2.1 AVHRR data.  
It contains a regional subset of sea surface temperature (SST) statistics for **January 2020** over the selected domain  
(18–31°N, 98–80°W).

## File: `regional_sst_subset.nc`

**Variables:**
- `sst_regional_mean(time)`  
  - Daily area-averaged SST time series over the chosen region.
- `sst_month_mean(lat, lon)`  
  - Map of the month-mean SST.
- `sst_month_std(lat, lon)`  
  - Map of intra-month variability (standard deviation).
- `sst_month_range(lat, lon)`  
  - Map of the monthly range (max – min).

**Dimensions:**
- `time` – daily values within the month (2020-01-01 to 2020-01-31).  
- `lat`, `lon` – spatial domain (18–31°N, 98–80°W).

## Notes
- Data source: [NOAA OISST v2.1](https://www.ncei.noaa.gov/products/optimum-interpolation-sst).  
- File created with Python, using **xarray** and **fsspec** to read directly from NOAA’s AWS S3 bucket.  
- Compression applied (`zlib=True, complevel=4`) to keep file size small for sharing.  