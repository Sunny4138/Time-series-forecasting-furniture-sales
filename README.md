# Time-series-forecasting-furniture-sales

This project focuses on forecasting monthly sales for the Furniture category from the Global Superstore dataset using the SARIMAX (Seasonal ARIMA with Exogenous Factors) model.
The model captures trend, seasonality, and cyclic patterns to provide accurate forecasting useful for retail planning, inventory management, and business decision-making.

# 🚀 Project Overview

- Performed time series analysis on retail furniture sales.

- Aggregated daily sales data into monthly time series.

- Conducted time series decomposition to understand:

- Trend

- Seasonality

- Residuals

- Used SARIMAX to model seasonal patterns.

- Performed parameter grid search using AIC scoring.

- Fitted final model:
- SARIMAX(1,1,1) × (1,1,0,12)

- Evaluated model using MSE and RMSE.

- Generated 100-step future forecasts with confidence intervals.

- Saved the fitted model using joblib.


# 🛠️ Technologies Used

Language:

- Python

Libraries:

- NumPy

- Pandas

- Statsmodels

- Matplotlib / Seaborn

- SciPy

- joblib

- warnings / itertools

Model:

- SARIMAX (Seasonal ARIMA)

# 📁 Folder Structure

```
.
├── data/
│   └── Global Superstore.xlsx
│
├── notebooks/
│   └── furniture_sales_forecasting.ipynb
│
├── models/
│   └── sarimax_furniture_model.pkl
│
├── screenshots/
│   ├── sales_plot.png
│   ├── decomposition_plot.png
│   ├── residual_diagnostics.png
│   ├── forecast_validation.png
│   └── future_forecast.png
│
├── requirements.txt
└── README.md
```

# 🧹 Data Preparation

1. Loaded the Global Superstore dataset.

2. Extracted only Furniture category rows.

3. Removed unnecessary columns:

- Shipping info

- Customer details

- Product details

4. Sorted by Order Date.

5. Grouped daily sales and resampled to monthly totals:
  ``` y = furniture['Sales'].resample('MS').sum()```

# 📉 Data Visualization

✔ Monthly sales plot

- Shows seasonal spikes at the end of each year.

✔ Time series decomposition

Breaks data into:

- Trend

- Seasonality

- Noise

This revealed strong year-end seasonality patterns.


# 🔧 SARIMAX Model Selection

- p, d, q → {0,1}

- P, D, Q → {0,1}, with seasonal period = 12

AIC scoring helped identify the best combination.

✔ Final Model

SARIMAX(1,1,1) × (1,1,0,12)


# 🔍 Model Diagnostics

Model diagnostics include:

- Standardized residual plot

- Residual histogram + KDE

- Q–Q plot

- ACF plot

These confirm the model fits the data well.

# 📊 Forecast Validation


One-step-ahead predictions (starting 2014 or your chosen date) compared with actual values.
Evaluation metrics:

- MSE: (208773864.27)

- RMSE: ( 14449.01)

The model accurately captures:

- Seasonal spikes

- Trend behaviour

- Month-to-month variation

# 🔮 Future Forecast (100 Steps)

- A 100-month future forecast was generated with 95% confidence intervals.
The interval widens over time—typical in time series forecasting.

# 💾 Saving the Model

``` joblib.dump(results, "sarimax_furniture_model.pkl") ```

# 📦 Installation

```
git clone https://github.com/your-username/furniture-sales-forecasting-sarimax.git 
cd furniture-sales-forecasting-sarimax 
pip install -r requirements.txt
```

# 💡 How to Run

 ```jupyter notebook notebooks/furniture_sales_forecasting.ipynb ```

 Or import the trained model:


 ```
 import joblib
model = joblib.load("models/sarimax_furniture_model.pkl")
```

# 📦 License

- This project is licensed for educational and research use.

# ✍️ Author

If you need help with time series modeling, SARIMAX tuning, or improving forecasting performance, feel free to reach out!

📩 Email: sunnyk36803@gmail.com

🔗 LinkedIn: https://www.linkedin.com/in/sunny30






