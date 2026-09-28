# Nigeria Multidimensional Poverty Index (MPI) Data Analysis

## Overview

This repository contains Python-based analysis of Nigeria's Multidimensional Poverty Index (MPI) data. The project explores multidimensional poverty across households and geographic areas, with additional analysis of poverty-related indicators by gender and state.

The analysis combines descriptive statistics, geographic aggregation and visualization, correlation analysis, and machine-learning approaches to examine patterns in multidimensional poverty and the indicators associated with poverty identification.

The project was developed as part of a data science application to official statistics, with a particular focus on using household-level survey data to generate subnational insights and explore how machine-learning methods can complement conventional statistical analysis.

---

## Objectives

The analysis was undertaken to:

* Examine household-level multidimensional poverty indicators.
* Aggregate MPI indicators at Local Government Area (LGA), state, and broader geographic levels.
* Explore the spatial distribution of selected poverty indicators across Nigeria.
* Examine relationships between MPI indicators using correlation analysis.
* Investigate the relative importance of individual poverty indicators using machine-learning methods.
* Develop classification models for identifying households according to the MPI poverty threshold.
* Explore differences in selected MPI indicators across gender and states.

---

## Notebooks

### 1. `Final_Data_MPI.ipynb`

The main notebook contains the broader MPI analysis workflow.

The notebook includes:

**Data preparation**

* Household-level data preparation.
* Removal of duplicate household records.
* Calculation of household size from individual-level records.
* Creation of household-level analytical data.

**Geographic analysis**

* Aggregation of MPI indicators by LGA, state, and zone.
* Calculation of indicator prevalence at geographic level.
* Examination of the number of observations available across LGAs.
* Joining analytical results with Nigerian administrative boundary data.

**Spatial visualization**

* Mapping of selected MPI indicators across Nigerian LGAs.
* Geographic visualization of indicators including sanitation, food security, and school attendance.

**Exploratory analysis**

* Examination of MPI variables and their distributions.
* Correlation analysis between indicators.
* Visualization using correlation matrices and other plots.

**Machine learning**

* Construction of poverty classification variables using the MPI poverty threshold of 26%.
* Exploration of Random Forest models and feature importance.
* Comparison and experimentation with additional classification approaches, including Logistic Regression, Support Vector Machines, and Gradient Boosting.
* Cross-validation and model evaluation.

The notebook therefore moves from data preparation and descriptive analysis through geographic analysis and exploratory machine-learning applications.

---

### 2. `Gender_MPI.ipynb`

This notebook focuses specifically on examining MPI indicators by gender and state.

The analysis includes:

* Aggregation of MPI indicators by sex and state.
* Use of survey weights in the analysis.
* Examination of selected indicators including nutrition, food security, health, education, housing, cooking, assets, unemployment, underemployment, and security shocks.
* Comparison of indicators across gender groups and Nigerian states.
* Visualization using line, bar, and dot plots.

The notebook provides a more focused view of how selected dimensions of multidimensional poverty vary across gender and geographic location.

---

## Methodology

The analysis follows a general workflow:

```text
Household / Individual-Level Data
              │
              ▼
        Data Preparation
              │
              ▼
      Household-Level Dataset
              │
              ├───────────────┐
              ▼               ▼
     Geographic Analysis   Exploratory Analysis
              │               │
              ▼               ▼
       LGA/State Results   Correlations &
              │             Distributions
              ▼
       Spatial Mapping
              │
              ▼
       Machine Learning
              │
              ▼
   Poverty Classification
```

The MPI poverty identification threshold used in the classification analysis is **26%**. Households with an MPI score at or below this threshold are classified according to the poverty definition implemented in the notebook.

Machine-learning models explored in the analysis include Random Forest, Logistic Regression, Support Vector Machine (SVM), and Gradient Boosting.

---

## Geographic Analysis

The main notebook aggregates household-level indicators to geographic units, particularly Local Government Areas (LGAs).

Selected indicators are converted into percentages at the geographic level and subsequently joined to administrative boundary data for visualization.

This allows the analysis to examine how different dimensions of deprivation vary spatially across Nigeria.

---

## Machine Learning

Machine-learning methods are used as an exploratory component of the project rather than as a replacement for the official MPI methodology.

The analysis explores whether household-level deprivation indicators can be used to classify households according to the MPI poverty threshold.

The notebook also examines feature importance from tree-based models to investigate which indicators contribute most strongly to the classification task.

Model evaluation includes train/test splits and cross-validation for selected models.

Because the MPI classification target is derived from the MPI itself, the machine-learning results should be interpreted as an analytical exploration of the relationship between the underlying deprivation indicators and MPI poverty identification, rather than as an independent alternative measure of poverty.

---

## Data

The analysis uses Nigeria MPI household-level survey data together with geographic boundary data for Nigeria.

The underlying household-level data are **not included in this repository** because the source data may contain restricted or non-public information.

To reproduce the analysis, users would need access to the appropriate source datasets and administrative boundary files.

A placeholder `data/README.md` can be used to document:

* The source of the data.
* Dataset descriptions.
* Required variables.
* Geographic boundary source.
* Any access restrictions.
* Instructions for placing the data in the expected directory.

---

## Tools and Technologies

The project uses Python and several libraries from the data science and geospatial ecosystem.

### Core tools

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* GeoPandas

### Analysis

* Data cleaning and transformation
* Aggregation and descriptive statistics
* Correlation analysis
* Survey-weighted analysis
* Geographic analysis
* Data visualization
* Machine learning
* Classification
* Cross-validation

---

## Repository Structure

```text
nigeria-mpi-data-analysis/
│
├── README.md
│
├── notebooks/
│   ├── Final_Data_MPI.ipynb
│   └── Gender_MPI.ipynb
│
├── data/
│   └── README.md
│
├── outputs/
│   ├── figures/
│   └── tables/
│
├── models/
│   └── README.md
│
├── requirements.txt
│
└── .gitignore
```

---

## Reproducibility

The notebooks were developed in Jupyter using Python.

Before running the notebooks, install the required Python packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn geopandas openpyxl joblib
```

Then launch Jupyter:

```bash
jupyter notebook
```

The source data and geographic boundary files should be placed in the directories specified in the notebooks.

For reproducibility, the notebooks should be run sequentially from the beginning after the required data files have been provided.

---

## Limitations

This repository represents an analytical exploration of MPI data and machine-learning approaches.

Several considerations are important when interpreting the results:

* The machine-learning classification target is derived from the MPI poverty definition and is therefore not an independent outcome variable.
* Results depend on the quality, completeness, and representativeness of the underlying survey data.
* Geographic estimates may be affected by differences in the number of observations available across LGAs.
* Survey weights and aggregation procedures need to be considered when interpreting geographic and gender comparisons.
* Machine-learning feature importance should be interpreted as model-based association rather than causal influence.
* The machine-learning experiments should not be interpreted as replacing the established MPI methodology.

---

## Purpose

The project demonstrates how household survey data, geospatial methods, and machine-learning techniques can be combined to support analysis of multidimensional poverty.

It is particularly relevant to the use of data science within official statistics, where conventional statistical production can be complemented by computational methods for exploratory analysis, visualization, geographic disaggregation, and analytical research.

---

## Author

**Emmanuel Omokhomion**

Data & Statistics | Data Science | Official Statistics | Geospatial Analysis

---

## License

This repository is intended for research, learning, and portfolio purposes. The underlying survey data remain subject to their original ownership, access, confidentiality, and usage conditions.
