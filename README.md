
# 📈 Time Series Analysis Shiny App

This interactive R Shiny App enables detailed **exploration, visualization, modeling, and forecasting** of time series data. It supports ARIMA, ARCH, GARCH models, includes stationarity testing and transformation, and provides comprehensive diagnostics and forecasting tools.

---

## 📂 Features Overview

### 1. **Data Handling & Preprocessing**
- Upload `.csv` file and select the appropriate column for time series.
- Handles **missing values** using mean imputation.
- Removes **duplicate records** automatically.
- Converts the selected data into a proper time series object.

### 2. **Exploratory Data Analysis (EDA)**
- Displays summary statistics.
- Shows **null values and duplicates**.
- Automatically cleans the data.
- Visualizations: Histogram, Boxplot, Density plot.

### 3. **Stationarity Analysis**
- Performs **ADF (Augmented Dickey-Fuller)** test to check stationarity.
- If non-stationary, applies:
  - Log Transformation
  - Differencing (Seasonal + Regular)
  - Moving Average Smoothing
- Plots **Original vs Stationary** time series.

### 4. **ACF/PACF Visualization**
- Provides plots of **ACF and PACF**:
  - For original series.
  - For stationary series.
- Assists in model order identification.

### 5. **Model Recommendation**
- Based on stationarity and ACF/PACF patterns, suggests:
  - AR, MA, ARIMA
  - ARCH/GARCH (if conditional heteroskedasticity exists)

### 6. **Model Fitting**
- User can choose:
  - AR
  - MA
  - ARIMA (manual or auto)
  - ARCH
  - GARCH
- Uses appropriate functions: `arima()`, `auto.arima()`, `garchFit()` from **rugarch** or **tseries**.

### 7. **Model Diagnostics**
- Residual plots and **ACF/PACF of residuals**
- QQ plot and Shapiro-Wilk test for normality
- Ljung-Box test for autocorrelation
- Conditional heteroskedasticity check

### 8. **Forecasting**
- Forecast horizon: user-defined
- Forecast plots for:
  - Time series prediction (mean)
  - Conditional sigma (for GARCH)
- Supports both **rolling** and **static** forecasts

### 9. **UI/UX Enhancements**
- Organized tabs and layout
- Drop-downs, sliders, and conditional panels
- Styled with Bootstrap components

### 10. **Download Options**
- Users can download:
  - Forecast results
  - Cleaned data
  - Model summary

---

## 🛠️ Technologies & Libraries

- **R Shiny** – Web framework
- **Tidyverse** – Data wrangling
- **forecast** – ARIMA modeling
- **tseries** – ADF test, GARCH modeling
- **rugarch** – Advanced GARCH models
- **ggplot2** – Data visualization

---

## 📌 Setup Instructions

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/TimeSeries-ShinyApp.git
   cd TimeSeries-ShinyApp
   ```

2. Install required packages in R:
   ```R
   install.packages(c("shiny", "forecast", "tseries", "rugarch", "ggplot2", "zoo", "FinTS", "TTR", "shinythemes", "DT"))
   ```

3. Run the app:
   ```R
   shiny::runApp("grp1_team_task")
   ```

---

## 📘 Interpretation Guide

### Stationarity
- Non-stationary series can mislead modeling.
- Look for constant mean/variance and flat ACF.

### ACF/PACF
- Sharp cutoff in PACF → AR model.
- Sharp cutoff in ACF → MA model.
- Slowly decaying → ARMA/ARIMA model.

### Residual Diagnostics
- Residuals should be white noise.
- No autocorrelation (Ljung-Box p > 0.05)
- Normal residuals (QQ plot + Shapiro test)

### ARCH/GARCH
- If residual variance changes over time, GARCH is preferred.
- ACF of squared residuals shows volatility clustering.

---

## 📈 Forecasting Insights

- Use `auto.arima()` if unsure about the order.
- Forecast horizon should match your practical requirement (e.g., 12 months for yearly).
- For financial data: ARCH/GARCH captures volatility well.

---

## 👥 Team Contributions

| Member | Role |
|--------|------|
| Person 1 | UI Design & Integration |
| Person 2 | Data Handling & Cleaning |
| Person 3 | Graphical Analysis & ACF/PACF |
| Person 4 | Model Implementation |
| Person 5 | Diagnostics, Forecasting, Download & UI Polishing |

---

## 📤 Future Enhancements
- Add support for **Seasonal ARIMA (SARIMA)**
- Integrate **Neural Network models**
- Deploy online via **Shinyapps.io**

---
