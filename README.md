# Time Series Forecasting: NYC Air Quality Index (AQI)

This project develops time series forecasting models to predict Air Quality Index (AQI) trends in **Manhattan, New York City**, with a focus on understanding key environmental drivers such as weather conditions and pollutant levels.

---

## 📊 Project Overview

**Problem:**  
Manhattan, the smallest yet most densely populated borough of NYC, faces persistent air quality challenges driven by:
- Heavy vehicle emissions
- Aging building boilers
- Weather patterns

**Goal:**  
Forecast AQI levels and investigate the impact of weather conditions on air pollution using historical data and time series modeling.

---

## 📂 Data Source & Structure

- **Source:** [OpenWeatherMap](https://openweathermap.org/)
- **Period:** January 1, 2000 – December 31, 2024
- **Records:** 9,000+ daily observations
- **Features:**
  - Date, AQI, Main Pollutant, CO, Ozone, PM10, PM2.5, NO2
  - Weather data: Temperature, Humidity, Wind Speed

---

## 🔍 Key Insights from EDA

- **AQI Trend:** Overall decreasing trend with less frequent extreme spikes post-2010.
- **Carbon Monoxide:** Significant decline over time.
- **Seasonality:** Clear annual and weekly cycles; AQI peaks during summer months.
- **Autocorrelation:** AQI shows strong dependence on past values (3-day cycles observed).

---

## 🛠️ Time Series Decomposition

- **Classical Decomposition:** Identified basic trend but struggled with complex seasonality.
- **STL Decomposition:** Successfully captured both yearly and weekly seasonal patterns.

---

## 📈 Forecasting Models Evaluated

| Model                | RMSE  | MAE   | MASE  | AIC      | BIC      |
|---------------------|-------|-------|-------|----------|----------|
| Naïve               | 20.9  | 14.5  | 0.79  | --       | --       |
| Seasonal Naïve      | 23.9  | 16.7  | 0.91  | --       | --       |
| ARIMA               | 16.7  | 12.0  | 0.65  | 74,239   | 74,289   |
| SARIMA              | 15.9  | 11.3  | 0.62  | 73,351   | 73,387   |
| **SARIMAX (Best)**  | 14.6  | 10.3  | 0.56  | 71,917   | 71,973   |

✅ **SARIMAX** provided the most accurate forecasts, incorporating both seasonality and exogenous variables.

---

## 🌦️ Weather Impact on AQI

- **Wind Speed:** Strongest predictor; higher wind speeds significantly reduce AQI by dispersing pollutants.
- **Temperature:** Weak positive effect; higher temperatures can increase AQI by promoting ozone formation.
- **Humidity:** Minimal impact on AQI.

---

## 🔁 Final Model

**SARIMAX Model Structure:**
- Seasonal: 3-day cycle
- Exogenous variables: Temperature, Humidity, Wind Speed
- Lowest RMSE, MAE, AIC, and BIC across all models

---

## 🛠️ Technologies Used

- Python
- Pandas, NumPy, Matplotlib
- Statsmodels (ARIMA, SARIMA, SARIMAX)
- Scikit-learn
- Time Series Decomposition (Classical & STL)

---

## 👥 Contributors

- Apoorva Prakash
- Halleluya Mengesha
- Hira Stanley
