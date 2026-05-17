# Cybersecurity Readiness Index (CRI)

DAV CA1 | BSc (Honours) Computing in Software Development | DKIT  
Author: Alexandru Gabriel Radu (D00258114) | Due: 20 May 2026

## What this project is

For this CA I built a composite indicator called the Cybersecurity Readiness Index (CRI). It produces a single score that ranks countries by how prepared they are for cybersecurity threats. The idea is similar to the UN Human Development Index, where you combine several different measurements into one overall score.

The CRI is broken down into four sub-indices:

- **Technical Capacity** - internet penetration, GCI technical pillar score, NCSI overall score
- **Legal and Regulatory Framework** - GCI legal pillar score
- **Capacity Building** - GCI capacity development pillar score
- **Organisational Measures** - GCI organisational and cooperation pillar scores

## Data sources

- Kaggle Cyber Security Indexes dataset (GCI, NCSI, DDL scores)
- ITU Global Cybersecurity Index 2024 pillar scores via World Bank Data360
- World Bank Open Data (internet penetration, GDP per capita)
- UN Human Development Index 2023

The dataset covers 35 countries across a range of income levels and regions.

## How to run

Install dependencies:

```bash
pip install -r requirements.txt
```

Place the raw data files in `data/raw/`:

- `cyber_security_kaggle.csv` - from Kaggle
- `ITU_GCI.csv` - from World Bank Data360
- `worldbank_internet.csv` - World Bank IT.NET.USER.ZS
- `worldbank_gdp.csv` - World Bank NY.GDP.PCAP.CD
- `HDR_HDI.xlsx` - UN HDR Statistical Annex

Then launch Jupyter and run the notebooks in order:

```bash
jupyter notebook
```

1. `01_data_collection.ipynb` - load and merge all datasets
2. `02_imputation.ipynb` - handle missing values
3. `03_multivariate_analysis.ipynb` - PCA and correlation analysis
4. `04_clustering.ipynb` - KMeans and hierarchical clustering
5. `05_normalisation_aggregation.ipynb` - normalise and build CRI scores
6. `06_regression_comparison.ipynb` - compare CRI against ITU GCI and HDI
7. `07_visualisation.ipynb` - all final charts and maps

## Project structure

```
dav-ca1/
├── data/
│   ├── raw/            # Downloaded data files (gitignored)
│   └── processed/      # Cleaned and merged CSVs
├── notebooks/
├── report/
│   ├── figures/        # Chart exports
│   └── report.md
├── .gitignore
├── requirements.txt
└── README.md
```
