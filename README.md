# Plastic Waste Circularity Index for Ghana

### With Emphasis on Flexible Packaging

A data-driven analytical framework for assessing plastic waste circularity in Ghana, with particular attention to flexible packaging such as sachets, films and pouches.

## Project Overview

Plastic waste management is a growing environmental and resource-management challenge in Ghana. While recycling and recovery are important components of a circular economy, circularity also depends on collection systems, reuse, leakage prevention and the ability to keep materials within productive cycles.

This project develops a **Plastic Waste Circularity Index (PWCI) framework for Ghana** using a synthetic dataset designed to demonstrate how plastic waste flows can be measured, analysed and visualised.

The project places particular emphasis on **flexible plastic packaging**, including:

* Sachets
* Films
* Pouches

These are compared with selected rigid packaging categories:

* Bottles
* Containers

The project combines material-flow accounting, circularity metrics, exploratory data analysis, statistical-ready datasets and interactive business-intelligence visualisation.

> **Important:** The dataset used in this project is synthetic and was created for analytical and methodological demonstration. It is not official national plastic-waste statistics for Ghana.


## Research Problem

Plastic waste management systems can generate large amounts of information about collection, recycling, recovery, disposal and leakage. However, these individual indicators do not always provide an integrated view of how effectively a waste stream is moving toward circularity.

A particular challenge exists for flexible packaging because lightweight films, sachets and pouches can be difficult to collect, sort and recycle economically.

This project therefore asks:

> **How can a data-driven circularity index be developed to evaluate plastic waste management performance in Ghana, particularly for flexible packaging?**

---

## Project Objectives

The project aims to:

1. Develop a structured plastic-waste material-flow dataset.
2. Validate the consistency of waste-flow data using mass-balance accounting.
3. Develop a simple circularity index based on reuse, recycling and recovery.
4. Calculate collection, recycling, recovery, reuse and leakage indicators.
5. Compare rigid and flexible plastic packaging.
6. Examine differences across regions and packaging types.
7. Identify relationships between waste-management indicators and circularity.
8. Develop an interactive Power BI dashboard for decision support.
9. Develop an Excel-based analytical model.
10. Establish a reproducible analytical workflow that can later be extended with statistical analysis in R and additional scenario modelling.

---

# Dataset

The analytical dataset contains:

* **1,050 observations**
* **18 original variables**
* **29 variables after analytical feature engineering**

The dataset represents a synthetic multi-year, multi-region plastic-waste system.

### Geographic coverage

Six Ghanaian regions are represented:

* Greater Accra
* Ashanti
* Western
* Central
* Eastern
* Northern

### Plastic categories

The dataset distinguishes between:

**Flexible packaging**

* Sachets
* Films
* Pouches

**Rigid packaging**

* Bottles
* Containers

---

## Original Variables

| Variable                 | Description                                     |
| ------------------------ | ----------------------------------------------- |
| `Year`                   | Observation year                                |
| `Region`                 | Geographic region                               |
| `Plastic_Type`           | Plastic material category                       |
| `Packaging_Type`         | Packaging format                                |
| `Flex_Class`             | Flexible or rigid classification                |
| `Waste_Generated_tonnes` | Estimated waste generated                       |
| `Collected_tonnes`       | Waste collected                                 |
| `Reused_tonnes`          | Waste/material reused                           |
| `Recycled_tonnes`        | Waste recycled                                  |
| `Recovered_tonnes`       | Waste recovered through other recovery pathways |
| `Landfilled_tonnes`      | Waste sent to landfill                          |
| `Burned_tonnes`          | Waste burned                                    |
| `Leaked_tonnes`          | Waste leaking from the managed system           |
| `Collection_Cost_GHS`    | Collection cost                                 |
| `Recycling_Value_GHS`    | Estimated recycling value                       |
| `Carbon_Emission_tCO2e`  | Estimated carbon emissions                      |
| `Leakage_Risk_Score`     | Leakage-risk measure                            |
| `Circularity_Index`      | Original dataset circularity field              |

---

#  Material Balance Validation

A fundamental validation step was performed to ensure that generated plastic waste was accounted for across the major waste pathways.

The mass-balance equation is:

$$
W =
R_u + R_c + R_v + L + B + L_k
$$

Where:

* \(W\) = waste generated
* \(R_u\) = reused material
* \(R_c\) = recycled material
* \(R_v\) = recovered material
* \(L\) = landfilled material
* \(B\) = burned material
* \(L_k\) = leaked material

The analytical workflow checks whether:

```text
Waste Generated
=
Reuse
+
Recycling
+
Recovery
+
Landfill
+
Burning
+
Leakage


The maximum observed mass-balance error was approximately:

0.000000000004 tonnes

This is effectively numerical floating-point error and indicates that the generated dataset satisfies the intended mass-balance constraint.

# Circularity Framework

The project uses a recovery-oriented **Core Circularity** metric.

Core\ Circularity = {Reuse + Recycling + Recovery}/{Waste Generated}*  100


The metric represents the proportion of generated waste that remains associated with reuse, recycling or recovery pathways.

It is deliberately presented as a **project-specific analytical metric**, rather than as a universal definition of circularity.

---

# Supporting Indicators

Several supporting indicators were calculated.

### Collection Efficiency

Collection Efficiency = {Collected/Waste Generated}*100

### Recycling Efficiency

Recycling Efficiency = {Recycled/Collected} * 100

### Recovery Rate
Recovery Rate = {Recovered/Waste Generated} * 100

### Reuse Rate
Reuse Rate = {Reused/Waste Generated} * 100

### Leakage Rate
Leakage Rate = {Leaked/Waste Generated} * 100

### Landfill Rate
Landfill Rate = {Landfilled/ Waste Generated} * 100

### Burning Rate
Burning Rate = {Burned/ Waste Generated}* 100


# Key Analytical Results

Using the current analytical dataset, the overall results are approximately:

| Indicator             |     Result |
| --------------------- | ---------: |
| Core Circularity      | **17.68%** |
| Collection Efficiency | **53.84%** |
| Recycling Efficiency  | **21.93%** |
| Recovery Rate         |  **2.91%** |
| Reuse Rate            |  **2.96%** |
| Leakage Rate          | **17.51%** |

These values describe the behaviour of the **synthetic analytical system** and should not be interpreted as measured national values for Ghana.

---

# Exploratory Analysis

The Python workflow examines:

* Overall circularity
* Circularity by year
* Circularity by region
* Circularity by packaging type
* Flexible vs rigid packaging
* Waste-flow distribution
* Leakage patterns
* Recycling performance
* Correlations between circularity and waste-management variables

The analysis identified a strong positive relationship between recycling and the project's Core Circularity measure and a negative relationship between leakage and circularity.

Because the Core Circularity metric directly incorporates recycling and recovery, these correlations are interpreted as relationships within the constructed index rather than evidence of independent causal effects.

---

# Power BI Dashboard

The project includes an interactive Power BI dashboard designed to communicate the results to non-technical users.

### Dashboard components

The dashboard includes:

* Total waste generated
* Total waste collected
* Total recycled
* Total recovered
* Total leaked
* Overall circularity
* Circularity trends
* Regional comparison
* Packaging comparison
* Flexible vs rigid waste flows
* Leakage analysis

### Dashboard pages

**Page 1 — Ghana Overview**

Provides an overall view of the plastic-waste system.

**Page 2 — Flexible Packaging**

Focuses on sachets, films and pouches.

**Page 3 — Regional Analysis**

Allows comparison between the six regions represented in the dataset.

---

# Python Analysis

Python was used for:

* Data loading
* Data validation
* Data cleaning
* Numerical calculations
* Mass-balance validation
* Feature engineering
* Exploratory data analysis
* Correlation analysis
* Visualisation
* Creation of the analytics-ready dataset

Main libraries include:

pandas
numpy
matplotlib

# Excel Model

An Excel component is being developed to provide a user-friendly analytical interface.

Planned components include:

* Raw data
* KPI summaries
* Regional analysis
* Packaging analysis
* Circularity calculations
* Decision-support tables

Scenario analysis is currently treated as a **future extension** rather than part of the completed analytical model.



# R Statistical Analysis

Statistical analysis in R is planned as a future extension.

Potential future analyses include:

* Descriptive statistics
* Flexible vs rigid comparison
* ANOVA
* Post-hoc testing
* Correlation analysis
* Multiple regression
* Statistical diagnostics

The current project has not completed these analyses.


# Analytical Workflow

The project follows the workflow:

Dataset Design
      ↓
Data Generation
      ↓
Data Validation
      ↓
Mass-Balance Check
      ↓
Data Cleaning
      ↓
Feature Engineering
      ↓
Circularity Metrics
      ↓
Exploratory Data Analysis
      ↓
Power BI Visualisation
      ↓
Excel Decision-Support Model
      ↓
R Statistical Analysis
      ↓
Scenario Analysis
      ↓
Research Development


# Limitations

### 1. Dataset

The dataset was created for analytical and methodological demonstration.

It is **not official Ghana national plastic-waste data**.

### 2. Simplified circularity metric

The Core Circularity metric focuses on the proportion of waste associated with reuse, recycling and recovery.

It does not fully capture:

* Material quality
* Virgin-material substitution
* Product lifetime
* Multiple recycling cycles
* Downcycling
* Environmental impacts
* Economic impacts
* Social impacts
* Energy requirements
* Life-cycle impacts

### 3. No causal interpretation

Correlation results describe relationships within the constructed dataset and should not be interpreted as causal relationships.

### 4. Regional representation

The six regions represented in the synthetic dataset should not be interpreted as statistically representative estimates of actual regional waste generation.

### 5. Scenario modelling

Scenario analysis has not yet been incorporated into the completed project.

---

# Future Development

Future versions of the project may include:

* Statistical analysis using R
* Sensitivity analysis
* Scenario modelling
* Uncertainty analysis
* Monte Carlo simulation
* Integration with real Ghanaian waste datasets
* Material Flow Analysis
* Life Cycle Assessment
* Economic analysis
* Spatial/geographic analysis
* Improved circularity weighting
* Material-quality considerations
* Recycling-chain modelling
* Policy scenario evaluation



# Research Application

This project is being developed as a portfolio and research foundation for further work in:

* Industrial Ecology
* Circular Economy
* Plastic Waste Management
* Sustainable Packaging
* Material Flow Analysis
* Life Cycle Assessment
* Environmental Analytics
* Operations Analytics
* Sustainability Data Analytics


# Tools

| Tool       | Purpose                                |
| ---------- | -------------------------------------- |
| Python     | Data cleaning, validation and analysis |
| Pandas     | Data manipulation                      |
| NumPy      | Numerical calculations                 |
| Matplotlib | Visualisation                          |
| Power BI   | Interactive dashboard                  |
| Excel      | Analytical model                       |
| R          | Planned statistical extension          |
| Git/GitHub | Version control and reproducibility    |

---

# Reproducibility

The project is structured so that the analytical workflow can be reproduced from the provided dataset and Python notebook.

The analytics-ready dataset contains the engineered indicators used in the dashboard and subsequent analysis.

Future versions will include additional scripts and statistical outputs as the project develops.

---

# Author

Priscilla Annang-Akwetey

Quality Control | Packaging | Quality Management | Sustainability | Data Analytics

Research interests:

* Industrial Ecology
* Circular Economy
* Sustainable Packaging
* Life Cycle Assessment
* Plastic Waste Management
* Environmental and Operations Analytics
