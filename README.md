# When Weather Changes the City

I wanted to see whether New York's weather changes the kind of help residents ask from the city. This project combines three years of NYC 311 service-request counts with daily NOAA observations from Central Park, then follows the data from raw collection through assessment, cleaning, integration, and exploratory analysis.

## What I found

- Heat and hot-water complaints move strongly in the opposite direction of temperature (Spearman rho = **-0.91**).
- Street-noise complaints rise with temperature (Spearman rho = **0.82**).
- Heavy-rain days average **2.9 times** as many sewer complaints as dry days.
- Every borough records roughly **2.6-2.9 times** as many heat and hot-water requests on the coldest 10% of days; the Bronx has the strongest relative response and the highest cold-day volume.

## Data

- **NYC 311 Service Requests:** gathered through the NYC Open Data API and aggregated by day, complaint type, and borough.
- **NOAA Central Park weather:** manually downloaded from the GHCN-Daily archive for station `USW00094728`.

The analysis uses a fixed window from 2022 through 2024 so the results remain reproducible. Raw data and the cleaned combined dataset are stored separately, and the source links are documented in [`data/raw/source_links.txt`](data/raw/source_links.txt).

## Project structure

```text
.
├── NYC_Weather_and_311_Analysis.ipynb
├── data
│   ├── raw
│   └── cleaned
├── figures
├── PROJECT_CHECKLIST.md
└── requirements.txt
```

## Run it locally

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab NYC_Weather_and_311_Analysis.ipynb
```

Run the notebook from top to bottom. It uses the stored raw files by default, while keeping the complete NYC API gathering code in the notebook for reproducibility.

## A note on interpretation

This is an observational analysis. The patterns are strong and consistent, but they do not prove that weather alone caused each request. Reporting behavior, housing conditions, infrastructure, and borough population all shape the totals too.

The MIT license applies to the original code and writing in this repository. Source datasets retain their original terms.

