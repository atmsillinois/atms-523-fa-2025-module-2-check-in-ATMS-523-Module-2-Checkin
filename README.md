[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/p9TKJWzX)
# ATMS 523 Module 1 template repository

A GitHub template repository for short exercises on **xarray** with a small, cloud-hosted climate dataset.  
The included notebook loads *NOAA OISST v2.1 (daily sea surface temperature)* from the **AWS Public Datasets** program via **Zarr** (anonymous S3 access), computes some basic statistics, and draws a simple global map.

> After you push this to GitHub, mark it as a **Template repository** in the repo settings so others can click **Use this template**.

## Quick start (local)

1. **Create env** (Conda recommended):
   ```bash
   conda env create -f environment.yml
   conda activate xarray-climate
   ```
   or with pip:
   ```bash
   python -m venv .venv && source .venv/bin/activate
   pip install -r requirements.txt
   ```

2. **Launch Jupyter**:
   Use vscode or launch a jupyter lab instance on your local or remote machine:
   ```bash
   jupyter lab
   ```

3. Open `notebooks/01_xarray_oisst_exercises.ipynb` and follow the prompts.

4. Be sure to use the `xarray-climate` conda environment so you have the required libraries installed above.

## Data Notes

- **Dataset:** NOAA Optimum Interpolation Sea Surface Temperature (OISST) v2.1, **daily**  
- **Cloud location:** `s3://noaa-oisst-zarr` (public, no credentials required)  
- **Access method:** netCDF + fsspec/s3fs with `anon=True`  
- **Variable used:** `sst` (°C); OISST provides °C values already (check attributes).

## Learning goals

- Open a netCDF dataset in the cloud with xarray
- Inspect coordinates, variables, and metadata
- Lazy-load & chunk with Dask
- Subset in space/time
- Compute descriptive stats (mean, std, anomalies, seasonal cycle)
- Make a quick global map of a time-aggregated field
- Export a small NetCDF (Check in for Week 2)

## Attribution

- NOAA OISST v2.1 (NOAA/NCEI).
- Thanks to the Pangeo community for tools that make cloud datasets easy to use.
