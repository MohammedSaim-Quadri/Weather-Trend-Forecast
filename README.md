# Weather Forecasting and Anomaly Detection using Machine Learning

## 📘 Overview
This project explores weather forecasting and environmental anomaly detection using machine learning and statistical techniques. The workflow includes data cleaning, feature engineering, model training (XGBoost and ARIMA), advanced EDA, and anomaly detection using statistical thresholds and Isolation Forests.

---

## 📚 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Objective](#-objective)
- [Methodology](#-methodology)
- [Exploratory Data Analysis](#-exploratory-data-analysis)
- [Feature Engineering](#-feature-engineering)
- [Modeling](#-modeling)
- [Anomaly Detection](#-anomaly-detection)
- [Results](#-results)
- [Insights](#-insights)
- [Project Structure](#-project-structure)
- [Setup Instructions](#-setup-instructions)
- [License](#-license)
- [Acknowledgements](#-acknowledgements)

---

## 📊 Dataset

The dataset includes detailed weather readings over time, including:

- Temperature, humidity, UV index, visibility, precipitation  
- Wind power and speed  
- Air quality indices (PM2.5, PM10, CO, SO2, NO2, O3)  
- Weather conditions and timestamps  

---

## 🎯 Objective

- Perform thorough data cleaning and feature engineering for forecasting and anomaly detection  
- Forecast future weather values using ML and statistical models  
- Detect anomalies in weather behavior that may represent environmental risks or data errors  

---

## 🔬 Methodology

### Data Cleaning  
- Removed or imputed null values  
- Converted datetime for time series processing  

### EDA  
- Visualized feature distributions and relationships  
- Time series trend exploration  

### Feature Engineering  
- Lag features  
- One-hot encoding for categorical variables  
- Interaction features (e.g., `temp_diff`)  

### Modeling  
- Trained XGBoost Regressor on `temp_c` and others  
- Fitted ARIMA model for time series comparison  

### Anomaly Detection  
- Z-score based thresholding (|z| > 3)  
- Isolation Forest algorithm for unsupervised outlier detection  

---

## 📈 Exploratory Data Analysis

- Plotted distributions and box plots for each numerical variable  
- Heatmaps for correlation  
- Condition-wise frequency plots and interaction analyses  

---

## 🧰 Feature Engineering

- **Lag Variables**: precipitation lag of 1, 7 days  
- **Interaction Features**: `temp_diff`, dew point, wind power  
- **Categorical Encoding**: `condition_text`, air_quality indexes  

---

## 🔥 Modeling

### XGBoost  
- Fast and scalable boosting model  
- **Performance**:  
  - MAE: ~0.83  
  - RMSE: ~1.02  
  - R²: ~0.89  
- Feature importance shows top drivers of prediction  

### ARIMA  
- Used for baseline univariate forecasting  
- Achieved stationarity via differencing  
- **Performance**:  
  - RMSE: ~2.35 (less accurate than XGBoost)  

---

## 🚨 Anomaly Detection

### Z-Score method on numeric columns  
- Threshold: |z| > 3  
- Top anomaly-prone: `visibility_km`, `wind_power`, `air_quality_PM2.5`  

### Isolation Forest  
- Detected 583 anomalies  
- Flagged via `anomaly = -1` column  
- Visualized with red markers on timeseries plots  

---

## ✅ Results

- XGBoost outperformed ARIMA significantly  
- Wind Power and Air Quality indices are strong signals  
- Anomalies captured abrupt changes and possible data noise  

---

## 💡 Insights

- Environmental and weather variables show seasonal & structural patterns  
- Machine Learning, especially XGBoost, is effective for multi-feature temporal prediction  
- Anomaly detection methods add value in real-time monitoring scenarios  

---

## 📂 Project Structure
```
project/ 
├── data/ 
│ └── feature_eng_weather_data.csv 
├── notebooks/ 
│ ├── 01_data_exploration.ipynb 
│ ├── 02_feature_eng.ipynb 
│ ├── 03_model_training.ipynb 
│ └── 04_Adv.EDA_anomaly.ipynb 
├── models/ 
│ ├── xgboost_model.pkl 
│ └── arima_model.pkl 
├── report/ 
│ └── final_report.docx
├── README.md
```

---

## ⚙️ Setup Instructions

```bash
# Clone the repository
git clone https://github.com/your-username/weather-forecasting-ml
cd weather-forecasting-ml
```

```bash
# Install dependencies
pip install -r requirements.txt

# Run Notebooks
# Use JupyterLab or VSCode to open and run the `.ipynb` files
```

---
