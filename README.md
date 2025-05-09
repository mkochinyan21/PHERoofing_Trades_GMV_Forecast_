# US Contractor Market GTV Forecasting

**Author:** Marina Kochinyan  
**Capstone Project – BS Data Science, American University of Armenia**  
**Notebook:** `Capstone_Final_Marina_Kochinyan.ipynb`

## Overview

This project forecasts **Gross Transaction Value (GTV)** in the US contractor market across four key trades: **Plumbing**, **HVAC**, **Electrical**, and **Roofing**. It focuses on two segments: **Residential Service & Replacement (Resi S&R)** and **Commercial (Comm+)**.

By applying a mix of classical and machine learning time series models (SARIMA, XGBoost, CatBoost, Prophet), the project provides forward-looking insights to support business strategy for contractors, vendors, and investors.

## Getting Started

### Prerequisites

Ensure Python 3.8 or higher is installed. The following Python packages are used:

- `pandas`
- `numpy`
- `xgboost`
- `catboost`
- `prophet` (or `fbprophet`)
- `scikit-learn`
- `matplotlib`
- `openpyxl`
- `tqdm`
- `google-cloud-bigquery`
- `plotly` (optional)
- (find the full list in requirements.txt)

### Installation

To install the required packages:

```bash
pip install -r requirements.txt
```

## Data Source
Data preprocessing has already been completed.
The notebook starts by connecting to the following Google Sheet:

"Capstone Data Sheet - BLS + IBIS"

This sheet contains merged and cleaned quarterly data from:

BLS: Employment and wage data

IBIS: Industry revenue estimates for relevant contractor segments

FRED: US GDP data (GDPC1 series)


## Project Structure

```bash
Capstone_Final_Marina_Kochinyan.ipynb    # Main execution notebook
README.md                                # Project documentation
requirements.txt                         # List of required Python packages
Capstone Dashboard Final                 # Final Dashboard
```

## Main Steps
1. Connect to Data Source
Connect to the Google Sheet or its BigQuery version.
2. Feature Engineering
Leverage pre-engineered lag features, growth rates, and trade classifications.
3. Model Training
Forecasting is performed using four models:
- SARIMA
- XGBoost
- CatBoost
- Prophet
4. Model Evaluation
Evaluate models on each category using MAE, RMSE, and MAPE. Prophet consistently yields strong performance.

5. Forecasting
Predicts GTV by Trade + Business Focus for 8 quarters (2023–2024).

6. Export Results
Final outputs are written to BigQuery fact tables for visualization in Tableau.

## Outputs
- Forecast tables per category in BigQuery
- Tableau dashboard with interactive GTV insights
- MAE evaluation charts comparing all models
