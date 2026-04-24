# Cybersecurity Readiness Index (CRI)

DAV CA1 | BSc (Honours) Computing in Software Development | DKIT  
Author: Alex Radu | Due: 10 May 2026

## What this project is

For this CA I built a composite indicator called the Cybersecurity Readiness Index (CRI). It produces a single score that ranks countries by how prepared they are for cybersecurity threats. The idea is similar to the UN Human Development Index, where you combine several different measurements into one overall score.

The CRI is broken down into four sub-indices:

- **Technical Capacity** - internet penetration, broadband subscriptions, number of CERTs
- **Legal and Regulatory Framework** - cybercrime legislation, data protection laws
- **Capacity Building** - education programmes, R&D spending, certified professionals
- **Organisational Measures** - national strategy published, government CIRT, public-private partnerships

## Data sources

- NCSI (National Cyber Security Index) - https://ncsi.ega.ee
- ITU Global Cybersecurity Index 2024 - https://www.itu.int/en/ITU-D/Cybersecurity/Pages/global-cybersecurity-index.aspx
- World Bank Open Data - https://data.worldbank.org
- UN Human Development Index - https://hdr.undp.org/data-center/human-development-index

The dataset covers 35 countries across a range of income levels and regions.

## How to run

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the raw data files and place them in `data/raw/`:

- `ncsi.csv` from https://ncsi.ega.ee
- `itu_gci_2024.csv`
- `worldbank_internet.csv`
- `worldbank_broadband.csv`
- `worldbank_gdp.csv`
- `hdi_2023.csv`

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
