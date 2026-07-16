# Forecasting Electricity Prices in Poland: Day-Ahead Market Analysis

## Project Overview

This repository contains the Python code developed as part of my master’s thesis titled:

**“Forecasting Electricity Prices in Poland – Analysis of Day-Ahead Market Data.”**

The project focuses on identifying relationships between hourly electricity prices in Poland’s day-ahead market and selected market, system and weather-related variables. It also compares several statistical and machine learning models for forecasting hourly electricity prices.

The analysis is based on 8,760 hourly observations covering the full calendar year of 2025.

## Research Objectives

The main objectives of the project were to:

- analyze the characteristics and variability of electricity prices in Poland’s day-ahead market,
- identify relationships between electricity prices and selected explanatory variables,
- examine the effects of electricity demand and renewable energy generation on market prices,
- develop forecasting models for hourly electricity prices,
- compare forecasting performance using multiple evaluation metrics.

## Research Questions

The analysis addresses the following research questions:

1. What relationships exist between day-ahead electricity prices and selected variables, particularly electricity demand, temperature and renewable energy generation?
2. Which forecasting model provides the most accurate predictions of hourly day-ahead electricity prices?

## Dataset

The analysis uses hourly data for Poland covering the period from **1 January 2025 to 31 December 2025**.

The dataset includes variables describing:

- day-ahead market electricity prices,
- balancing market prices,
- electricity demand in the Polish power system,
- differences between actual and planned electricity demand,
- cross-border electricity exchange,
- wind generation share,
- photovoltaic generation share,
- combined renewable energy generation share,
- average temperature in Poland,
- calendar-related variables such as hour, weekday, month and weekend indicators.

### Data Availability

The Excel dataset used in the analysis is not included in this repository and will not be published.

The repository contains only the analytical code and model implementation. As a result, the notebook cannot be executed directly without access to a dataset with the required structure and variables.

## Methodology

The analytical workflow includes the following stages:

### 1. Data Preparation

- loading data from an Excel workbook,
- standardizing column names,
- converting variables to appropriate data types,
- sorting observations chronologically,
- validating data completeness,
- creating calendar-based features,
- preparing lagged variables for time-series forecasting.

### 2. Exploratory Data Analysis

The exploratory analysis includes:

- descriptive statistics,
- identification of negative and unusually high electricity prices,
- monthly, weekly, and hourly aggregations,
- electricity price distribution analysis,
- analysis of seasonal and intraday patterns,
- visualization of electricity prices, demand and renewable generation.

### 3. Statistical Analysis

The relationships between electricity prices and explanatory variables were assessed using:

- Pearson correlation coefficients,
- Spearman rank correlation coefficients,
- scatter plots,
- the Augmented Dickey–Fuller stationarity test,
- ordinary least squares regression,
- heteroskedasticity- and autocorrelation-consistent standard errors.

### 4. Forecasting Models

The following forecasting approaches were compared:

- previous-day price benchmark,
- previous-week price benchmark,
- autoregressive linear model,
- linear regression with exogenous variables,
- Ridge regression,
- Lasso regression,
- HistGradientBoostingRegressor.

The forecasting features include lagged electricity prices and selected lagged explanatory variables.

## Model Evaluation

The dataset was divided chronologically into:

- **80% training data**
- **20% test data**

The models were evaluated using:

- Mean Absolute Error — MAE,
- Root Mean Squared Error — RMSE,
- Symmetric Mean Absolute Percentage Error — sMAPE,
- Relative Mean Absolute Error — rMAE.

A chronological split was used instead of random sampling to preserve the temporal structure of the data and prevent future observations from influencing model training.

## Key Findings

The analysis produced the following main findings:

- higher electricity demand was generally associated with higher day-ahead electricity prices,
- higher renewable energy generation was associated with lower electricity prices,
- photovoltaic generation showed a particularly strong negative relationship with day-ahead prices,
- electricity prices demonstrated clear monthly, weekly, and intraday patterns,
- negative electricity prices occurred during periods of high supply and relatively low demand,
- models using both historical prices and additional explanatory variables generally performed better than simple historical benchmarks,
- the Lasso regression model achieved the best forecasting performance among the evaluated models.

## Technologies and Libraries

The project was developed in Python using a Jupyter Notebook.

Main libraries:

- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`
- `scikit-learn`
- `openpyxl`
