# Task_Kovai.co
# Public Transport Time Series Forecasting

This repository contains a **time series forecasting project** using Gradient Boosting models to predict public transport usage trends. The project focuses on multiple transport types, including Local Route, Light Rail, Peak Service, Rapid Route, and School services.

---


## Project Overview

The goal of this project is to **forecast public transport demand** using historical data. By leveraging Gradient Boosting models, we aim to capture complex patterns in time series data and provide accurate predictions for different transport services.

---

## Data Description

The dataset contains daily public transport usage data, including:

| Column         | Description                          |
|----------------|--------------------------------------|
| Local Route    | Number of passengers on local routes |
| Light Rail     | Number of passengers on light rail   |
| Peak Service   | Number of passengers during peak     |
| Rapid Route    | Number of passengers on rapid routes|
| School         | Number of students using transport   |
| Date           | Date of observation                  |

---

## Features

- Time-based lag features (e.g., past 5 days)  
- Correlated variables for multivariate forecasting  
- Optional additional features like day-of-week, holidays, or trend indicators  

---

## Correlation Analysis

Strong correlations observed between transport types:

| Variables                | Correlation |
|--------------------------|------------|
| Local Route - Light Rail | 0.919      |
| Local Route - Peak Service | 0.944    |
| Local Route - Rapid Route | 0.965     |
| Local Route - School      | 0.852     |
| Light Rail - Peak Service | 0.879     |
| Light Rail - Rapid Route  | 0.968     |
| Peak Service - Rapid Route | 0.945    |
| Peak Service - School     | 0.729     |
| Rapid Route - School      | 0.754     |

> Highly correlated features were considered when selecting predictors for the Gradient Boosting model.

---

## Modeling Approach

- **Model:** SARIMA
- **Input:** Lag features of each transport type  
- **Output:** Forecast for future demand  
- **Evaluation Metrics:** RMSE, MAE, MAPE  

**Steps:**
1. Create lag features for each variable  
2. Split data into training and testing sets  
3. Train Gradient Boosting model  
4. Forecast future values  
5. Evaluate predictions  

---
## Insights

**Decrease in passenger ridership during COVID-19**  
- Seasonal decomposition shows a clear drop in usage during the pandemic period.

**Lower passenger count on weekends**  
- Weekend ridership is consistently lower than on weekdays.

**Rapid Route is the most used service**  
- Over 39% of passengers prefer the Rapid Route, making it the most popular service.

**Seasonal dips at year-end**  
- Every year-end shows a seasonal dip in passenger numbers, likely due to holidays and reduced travel.

Every year-end shows a seasonal dip in passenger numbers, likely due to holidays and reduced travel.

Strong correlations between transport types

High correlation (>0.9) exists between Local Route, Rapid Route, Peak Service, and Light Rail, indicating similar usage patterns across services.
