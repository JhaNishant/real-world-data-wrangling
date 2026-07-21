# When Weather Changes the City

Weather changes New York. This analysis asks if it also changes the help that residents request from the city. It combines three years of NYC 311 counts with daily NOAA weather data from Central Park. The work covers collection, checks, cleaning, joining, and analysis.

## What the data shows

* Heat and hot water complaints fall as temperature rises. Spearman rho is **negative 0.91**.
* Street noise complaints rise with temperature. Spearman rho is **0.82**.
* Heavy rain days average **2.9 times** as many sewer complaints as dry days.
* Every borough has about **2.6 to 2.9 times** as many heat and hot water requests on the coldest 10 percent of days. The Bronx has the largest increase and the highest cold day volume.

## Data

* **NYC 311 Service Requests:** gathered through the NYC Open Data API and grouped by day, complaint type, and borough.
* **NOAA Central Park weather:** downloaded from the GHCN Daily archive for station `USW00094728`.

The analysis uses a fixed window from 2022 through 2024 so the results remain reproducible. Raw data and the cleaned combined dataset are stored separately, and the source links are documented in [`data/raw/source_links.txt`](data/raw/source_links.txt).

## Repository structure

```text
.
├── NYC_Weather_and_311_Analysis.ipynb
├── data
│   ├── raw
│   └── cleaned
├── figures
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
