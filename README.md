# Vehicle Registration Trend Analysis

Course-end project for B.E. (IT), III-Sem, Chaitanya Bharathi Institute of Technology (CBIT), A.Y. 2026-27.

An end-to-end Python data-science project that analyses how the registered electric-vehicle fleet of Washington State has changed over time, organised by the five course outcomes (CO1–CO5) of the syllabus.

## Dataset

**Dataset file (direct download, CSV, about 33 MB):**
https://raw.githubusercontent.com/BogdanRivera/Electric_vehicle/main/Electric_Vehicle_Population_Data.csv

**Repository page:** https://github.com/BogdanRivera/Electric_vehicle

**Washington State Electric Vehicle Population Data** — published by the Washington State Department of Licensing (public domain).

| Item | Value |
|---|---|
| Rows / columns | 135,038 / 17 (134,726 rows after keeping Washington vehicles only) |
| One row is | one registered plug-in electric vehicle (BEV or PHEV) |
| Key columns | Model Year, Make, Model, Electric Vehicle Type, Electric Range, Base MSRP, County, City |
| Download | https://raw.githubusercontent.com/BogdanRivera/Electric_vehicle/main/Electric_Vehicle_Population_Data.csv |

The notebook downloads the file automatically if it is not in the project folder.

**Things to know about the data**

- It is a snapshot of vehicles registered *now* and has no registration date, so **Model Year is used as the time axis** (analysis covers 2010–2023).
- `Electric Range = 0` (42% of rows) and `Base MSRP = 0` (97% of rows) are placeholders for "not recorded", not real values. Battery range for almost all battery-electric vehicles from model year 2021 onward was never researched, so **range trends are valid only up to model year 2020**.
- The column named `Country` actually holds the county.

## Project files

| File | Description |
|---|---|
| `Vehicle_Registration_Trend_Analysis_Short.ipynb` | Main notebook (38 cells), executed, with outputs and plots |
| `Vehicle_Registration_Trend_Analysis.ipynb` | Longer version (128 cells) with more examples per topic |
| `Vehicle_Registration_Trend_Analysis_Report.pdf` | 28-page project report in the college format |
| `Vehicle_Registration_Trend_Analysis_Report.docx` | Editable Word copy of the report |
| `Electric_Vehicle_Population_Data.csv` | The dataset (also supplied as a `.zip`) |
| `outputs/` | Created when the notebook runs: CSV/TSV/JSON samples and saved figures |

## Course outcomes covered

| CO | Unit | Topics applied to the vehicle data |
|---|---|---|
| **CO1** | I – NumPy basics | ndarrays, dtypes, arithmetic and broadcasting, indexing and slicing, boolean and fancy indexing, transpose/swapaxes, pseudo-random numbers and bootstrap, universal functions |
| **CO2** | II – Pandas basics, data loading and storage | Series/DataFrame/Index, reindexing, dropping, selection and filtering, alignment, apply/map, sorting and ranking, duplicate labels, descriptive statistics, reading a CSV in chunks, writing CSV/TSV/JSON |
| **CO3** | III – Cleaning, preparation and wrangling | Missing data, replacing values, renaming, binning (`cut`/`qcut`), outliers, categorical type, hierarchical indexing, joins and merges, concat, `combine_first`, reshaping |
| **CO4** | IV – Aggregation and time series | Named aggregation, split-apply-combine, datetime conversion, date ranges and offsets, resampling (down/up-sampling) and interpolation |
| **CO5** | V – Plotting and visualization | Matplotlib figures/subplots, styles, ticks and legends, saving plots; Seaborn line, bar, histogram/KDE, scatter, FacetGrid and categorical plots |

Every notebook section is labelled with its CO and syllabus topic number (for example `# 3.7 Detecting and filtering outliers`).

## How to run

1. Install Python 3.10 or later and the libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn jupyter
   ```
   (pandas 2.x or newer and seaborn 0.12 or newer. The notebook was tested with pandas 3.0 and seaborn 0.13.)
2. Put the notebook and, optionally, `Electric_Vehicle_Population_Data.csv` in the same folder. If the CSV is missing, the first cell downloads it (internet needed once).
3. Start Jupyter and open the notebook:
   ```bash
   jupyter notebook Vehicle_Registration_Trend_Analysis_Short.ipynb
   ```
4. Choose **Kernel → Restart & Run All**. The notebook runs in well under a minute.

**Google Colab:** upload the notebook, run all cells; the dataset is downloaded automatically.

## Main results

- 134,726 Washington-registered electric vehicles after cleaning; **77.0% are battery-electric (BEV)**, the rest plug-in hybrids (PHEV).
- Model year 2022 is the largest cohort (27,920 vehicles); cohort size grew about **22% per year** from model year 2013 to 2022.
- The market is concentrated: **Tesla holds 45.8%** of vehicles, and Tesla, Nissan and Chevrolet together 64.0%. Tesla Model 3 and Model Y are the two most common models.
- **King County has 52.6%** of all vehicles; King, Snohomish and Pierce together have 71.6%.
- Real BEV range rose from about 111 miles (model year 2013) to 280 miles (model year 2020), roughly +10.7 miles per model year. PHEV range stayed between about 22 and 38 miles.

## Limitations

- Model year is a proxy for time, and scrapped or exported vehicles are absent (survivorship bias).
- Model year 2023 may be incomplete and 2024 is only partly present.
- Only plug-in electric vehicles are included, so the share of EVs in the whole vehicle fleet cannot be computed.
- The manufacturer-country lookup table used to demonstrate joins is hand-made and not part of the dataset.

## Libraries

NumPy, pandas, Matplotlib, Seaborn, Jupyter.

## Data source and credit

Washington State Department of Licensing, *Electric Vehicle Population Data* (public domain). Public GitHub mirror used for the download: https://github.com/BogdanRivera/Electric_vehicle
