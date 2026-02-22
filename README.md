# Time Series Forecasting: Iowa State House & Senate Expenditures

## Overview
This project analyzes and forecasts campaign expenditure trends for Iowa General Assembly committees (State House and State Senate). Using public datasets from the Iowa government open data portal, the project performs data cleaning, exploratory analysis, and time series forecasting using ARIMA/SARIMAX models.

## Business Problem
Campaign spending provides insight into political resource allocation and election-cycle dynamics. The goal is to:
- Understand expenditure trends over time
- Identify top spending committees and top recipient organizations
- Forecast future expenditure patterns using time series models

## Data
Public datasets (Iowa open data portal) including:
- Campaign Expenditures
- Campaign Contributions
- Registered Political Committees/Candidates

Filtered to **Committee Type = State House / State Senate**.  
(See project report for detailed data description and limitations.)

## Methods
### 1) Data Cleaning & Preparation
- Filtered to State House and State Senate committees
- Standardized missing values and date formats
- Address consolidation and validation
- Duplicate removal and year extraction

### 2) Exploratory Data Analysis (EDA)
Key patterns observed:
- Expenditures show cyclical peaks aligned with election years
- State House generally spends more than State Senate
- Recipient orgs include major party organizations and printing/media vendors

### 3) Forecasting (Time Series)
- Stationarity checks (ADF test) + differencing
- ARIMA baseline model
- SARIMAX model to better capture cyclical patterns

## Key Findings
- Expenditures and contributions show cyclical patterns with notable election-year spikes.  
- ARIMA forecasts showed instability (alternating high/low patterns), suggesting model structure limitations for this series.  
- SARIMAX improved smoothness and aligned better with cyclical behavior, though committee-level forecasts remained unstable due to limited annual observations and irregularities.  
- Negative expenditures exist in the data (likely adjustments/refunds/errors) and can distort forecasts if not handled.

## Repo Contents
- `notebooks/` - analysis notebook
- `report/` - final written report (PDF)
- `images/` - optional charts/screenshots

## How to Run
1. Open `notebooks/aksingh.ipynb`
2. Install dependencies (example):
   - pandas, numpy, matplotlib, statsmodels, scikit-learn
3. Run cells top to bottom

## Future Improvements
- Use monthly/quarterly aggregation (more data points) instead of annual to reduce model instability
- Apply log/Box-Cox transforms for variance stabilization
- Try Prophet / ETS / TBATS and compare backtesting metrics
- Build a small dashboard to show trends + forecasts
