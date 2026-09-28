# Nigeria Multidimensional Poverty Index (MPI) Data Analysis

This repository contains Python/Jupyter analysis of Nigeria Multidimensional Poverty Index (MPI) data. It brings together household-level data preparation, subnational aggregation, geospatial visualization, exploratory analysis, machine-learning classification, and gender/state analysis.

## Project objectives

The analysis explores:

- household-level MPI indicators and poverty identification;
- aggregation of deprivation indicators by Local Government Area (LGA), state and zone;
- geographic patterns in selected MPI indicators;
- relationships among deprivation indicators;
- machine-learning approaches for classifying households using the MPI poverty threshold; and
- differences in selected MPI indicators by sex and state.

## Notebooks

### `01_MPI_Data_Analysis.ipynb`

The main notebook covers data preparation, household-size construction, LGA-level aggregation, geospatial mapping, correlation analysis, feature importance, and classification experiments using Random Forest, Logistic Regression, Support Vector Machine (SVM), and Gradient Boosting.

The machine-learning section uses the MPI identification variable and a 26% threshold to construct a binary poverty-classification target. These models are treated as an analytical exploration rather than an alternative to the established MPI methodology.

### `02_Gender_and_State_MPI_Analysis.ipynb`

This notebook examines selected deprivation indicators by sex and state. The analysis uses the `Individual_Weight` variable to calculate weighted indicator prevalence and produces state-by-sex visualizations.

## Repository structure

```text
nigeria-mpi-data-analysis/
├── README.md
├── notebooks/
│   ├── 01_MPI_Data_Analysis.ipynb
│   └── 02_Gender_and_State_MPI_Analysis.ipynb
├── data/
│   ├── raw/
│   │   └── README.md
│   └── processed/
├── outputs/
│   ├── figures/
│   └── tables/
├── models/
├── requirements.txt
└── .gitignore
```

## Data

The underlying survey data are not included in this repository. Place authorized source files under `data/raw/` before running the notebooks. See `data/raw/README.md` for the expected files.

Do not publish restricted, confidential, personally identifiable, or otherwise non-public survey data to a public repository.

## Methodology

The main workflow is:

1. Read the individual/household survey data.
2. Retain one record per household and calculate household size from individual records.
3. Aggregate deprivation indicators to LGA, state and zone.
4. Calculate LGA-level indicator prevalence as percentages of households.
5. Join LGA results to administrative boundary data for mapping.
6. Explore relationships among deprivation indicators.
7. Construct a binary poverty-classification target using the 26% MPI threshold.
8. Train and evaluate several classification models.
9. Examine gender/state differences using survey weights.

## Important interpretation note

The machine-learning target is derived from the MPI identification measure, while the predictors include the underlying deprivation indicators. Consequently, model performance and feature importance should not be interpreted as independent evidence of causal determinants of poverty. The ML section is exploratory and intended to demonstrate how computational methods can complement conventional official-statistics analysis.

Geographic estimates should also be interpreted in light of differences in sample sizes across LGAs and the survey design/weighting approach used in the underlying data.

## Requirements

The notebooks use Python and common data-science/geospatial libraries. Install the dependencies with:

```bash
pip install -r requirements.txt
```

Then launch Jupyter:

```bash
jupyter notebook
```

## Reproducibility

The notebooks use relative paths so that they can be moved between machines. Before running them, place the authorized source datasets and, where required, the LGA administrative boundary shapefile in the locations described in `data/raw/README.md`.

The notebooks may create processed datasets, tables, figures and model files in the repository's `data/processed/`, `outputs/`, and `models/` directories. These generated files are ignored or intentionally left empty in the initial repository.

## Author

**Emmanuel Omokhomion**

Data & Statistics | Data Science | Official Statistics | Geospatial Analysis

## License / data access

This repository is intended for research, learning and portfolio purposes. The underlying survey data remain subject to their original ownership, confidentiality, access and usage conditions.
