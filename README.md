This detailed `README.md` for this R Shiny Time Series Analysis App includes:

- Overview  
- Features  
- Installation Instructions  
- Usage  
- Interpretation Guide for All Steps  
- Dependencies  
- Credits  

---

```markdown
# 📈 Time Series Analysis Dashboard in R Shiny

This is an interactive and educational Shiny web application designed for comprehensive time series analysis. It supports graphical exploration, stationarity checks, trend/seasonality decomposition, model fitting (ARIMA, ARCH, GARCH), diagnostics, and forecasting.

---

## 🔍 Features

- Upload and handle `.csv` time series data
- Exploratory Data Analysis (EDA) with handling of missing and duplicate values
- ACF/PACF visualization for both original and stationary series
- Automatic stationarity transformation (log transform, differencing)
- Stationarity testing (ADF Test)
- Model suggestions: AR, MA, ARMA, ARIMA, ARCH, GARCH
- Residual diagnostics and validation
- Forecasting with customizable horizon
- Download model results and plots
- Clean and interactive UI

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following R packages installed:

```r
install.packages(c("shiny", "ggplot2", "forecast", "tseries", "rugarch", "zoo", "FinTS", "TTR", "dplyr"))
```

### Run the App

Put the `ui.R` and `server.R` files in the same folder (e.g., `grp1_team_task`) and run:

```r
shiny::runApp("grp1_team_task")
```

---

## 📂 Usage Instructions

1. Upload your time series data in `.csv` format.
2. Select the column representing the time series.
3. Choose EDA to explore data quality and patterns.
4. View ACF/PACF plots of the original and stationary data.
5. The app automatically performs stationarity tests and applies transformations.
6. Choose the model to fit: AR, MA, ARMA, ARIMA, ARCH, GARCH, or Auto.
7. Set the forecast horizon and view forecast plots.
8. Download the summary and plots for reporting.

---

## 📖 Interpretation Guide

### Exploratory Data Analysis

- **Missing Values**: Shown as a count. Missing values are imputed using mean.
- **Duplicates**: Duplicated rows are removed before model fitting.
- **Trend/Seasonality**: Decomposed to visualize underlying components.

### Stationarity Checks

- **ADF Test**: Used to test for stationarity.
- **Differencing/Log Transform**: Automatically applied if data is non-stationary.
- **Interpretation**: Stationary series will have no trend/seasonal pattern and a flat ACF.

### ACF/PACF Plots

- **Original vs Stationary ACF/PACF**: Used for identifying appropriate model order.
  - ACF decays slowly → non-stationary.
  - ACF/PACF cutoffs suggest AR or MA order.

### Model Suggestions

- Based on AIC/BIC values and ACF/PACF structure.
- ARIMA(p,d,q) is selected using `auto.arima()` where applicable.
- ARCH/GARCH is recommended when residuals show volatility clustering.

### Residual Diagnostics

- **White Noise Check**: Residuals should show no pattern.
- **ACF of Residuals**: Should not show significant lags.
- **Ljung-Box Test**: Checks autocorrelation in residuals.

### Forecasting

- **Horizon**: User-specified number of steps to forecast.
- **In-Sample vs Out-of-Sample**: Forecasts shown with confidence intervals.
- **Interpretation**: Forecasts should align with data and residuals should remain white noise.

---

## 📦 Dependencies

- `shiny`
- `ggplot2`
- `forecast`
- `tseries`
- `rugarch`
- `FinTS`
- `zoo`
- `TTR`
- `dplyr`

---

## 🙌 Credits

Developed by a 5-member team as part of an academic project on Advanced Time Series Analysis.  
Includes implementation of Unit 1 and Unit 2 concepts such as ARIMA, stationarity, seasonal models, and GARCH.

---

## 📌 Note

- GARCH fitting requires enough data (generally > 50 points).
- If “wrong embedding dimension” appears, check data length or resample.

```
