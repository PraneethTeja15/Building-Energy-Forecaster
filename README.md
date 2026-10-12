# Building-Energy-Forecaster
An end-to-end machine learning pipeline using XGBoost to forecast building energy consumption 24 hours in advance on the ASHRAE dataset, featuring an interactive evaluation dashboard
An interactive end-to-end Machine Learning pipeline utilizing XGBoost to predict building energy consumption 24 hours in advance using the ASHRAE Great Energy Predictor III dataset.

Featuring a custom evaluation dashboard built with Plotly and IPywidgets to allow visual analysis of prediction performance across 17 distinct education buildings.

## 📊 Project Architecture
```
├── notebooks/
│   └── 01_explore.ipynb  # This main notebook
├── data/                                    # Raw dataset (Not pushed to Git)
│   ├── train.csv
│   ├── building_metadata.csv
│   └── weather_train.csv
├── results_core.csv                         # Saved core predictions for evaluation
├── metrics.csv                              # Building-by-building metrics
└── README.md                                # Project Documentation
```

## 🚀 Key Features & Pipeline
1. **Data Preprocessing & Selection**: Focused on high-quality electricity consumption profiles from 20 Education buildings with highly complete meteorological parameters.
2. **Feature Engineering**: Built rolling window statistics, lag features (24h and 168h), temporal profiles (hour of day, day of week, holiday markers), and weather variables.
3. **Low-Consumption Outlier Identification**: Diagnosed and excluded extreme low-energy buildings (Buildings 634, 638, and 639) that skewed evaluation metrics like MAPE (which dropped from 37.82% down to 16.20%).
4. **24-Hour Ahead Forecasting**: Configured a regression model to strictly perform day-ahead scheduling predictions using historical features available up to 24 hours prior.
5. **Interactive Evaluation Dashboard**: Built an integrated workspace dashboard to filter results and visualize real-time actual vs. predicted patterns.

## 📈 Results (Core 17 Education Buildings)
* **Baseline Model (24-Hour Lag Persistence)**: RMSE = 25.87, MAPE = 16.39%
* **XGBoost Day-Ahead Model**: **RMSE = 20.50, MAPE = 16.20%**

## 🛠️ Installation & Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/PraneethTeja15/building-energy-forecaster.git
   ```
2. Open `ASHRAE_Forecasting_Dashboard.ipynb` in Google Colab or your local Jupyter instance.
3. Run all cells to play with the interactive visualization dashboard.
"""
