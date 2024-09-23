# Tesla Stock Price Forecasting
## Project Overview
This project aims to forecast the stock price of Tesla (TSLA) using a combination of historical stock data, correlated stocks, and key economic indicators. The goal is to provide an accurate prediction model that can help trading firms make informed, data-driven investment decisions. The project explores both statistical (ARIMA/ARIMAX) and machine learning models, ultimately selecting Lasso Regression as the most effective approach.
## Problem Statement
Tesla's stock is known for its volatility and sensitivity to market dynamics, which makes accurate forecasting a challenge. The project focuses on building a robust predictive model using two years of historical data, correlated stocks (Nio, Rivian, Lucid, Ford, GM), and economic indicators such as interest rates, inflation (CPI), consumer confidence, and oil prices. The forecast aims to predict Tesla's stock price over a six-month horizon.
## Data Sources
- **Tesla Stock and Correlated Stocks (Nio, Rivian, Lucid, Ford, GM):** Data obtained via the Yahoo Finance API using the yfinance library.
- **Economic Indicators:**
    - Interest Rate and Inflation (CPI) from FRED.
    - Consumer Confidence Index from Investing.com.
    - Oil Prices from Macrotrends.
## Project Workflow
1. **Data Collection:** Acquired and cleaned historical stock and economic indicator data, interpolating monthly data to daily values for consistent analysis.
2. **Exploratory Data Analysis (EDA):**
    - Decomposed each time series into trend, seasonal, and residual components.
    - Conducted stationarity tests (ADF test).
    - Checked correlation, Granger causality, and cointegration between Tesla and other time series.
    - Plotted autocorrelation (ACF) and partial autocorrelation (PACF) to determine appropriate lags for modeling.
3. **Preprocessing:**
    - Created lag features (1-day, 4-day, and 30-day windows) to capture short- and medium-term patterns.
    - Engineered additional features, including date-related features.
4. **Modeling:**
    - Applied ARIMA and ARIMAX models to the time series data.
    - Implemented machine learning models (Linear Regression, Lasso, Ridge, and XGB Regressor).
    - Conducted time series cross-validation to evaluate performance metrics (RMSE, MAE, AIC, BIC).
5. **Evaluation:**
    - Lasso Regression was selected as the final model due to its strong performance in reducing overfitting and handling variable selection effectively.
    - Hybrid models combining ARIMA and Lasso were tested, but Lasso alone provided the most accurate forecast.
## Final Model
Lasso Regression was selected as the final model for Tesla's stock price forecasting. It outperformed both statistical models (ARIMA/ARIMAX) and other machine learning methods by eliminating irrelevant variables and improving generalization.
## Results
Lasso Regression provided the most accurate predictions for Tesla's stock price, with significant improvements in reducing overfitting compared to ARIMA-based models. Further work could explore additional external features, alternative machine learning techniques, and advanced models like LSTM for time series.
## Recommendations
- Incorporate alternative data sources like sentiment analysis (social media/news sentiment) or macroeconomic forecasts.
- Explore deep learning models such as LSTM to capture more complex patterns in stock prices.
- Expand the training dataset by including more historical data and other economic cycles to improve the model's robustness.
- Regularly retrain the model to keep up with stock market volatility.
## How to Run
1. Clone the repository:
```bash
git clone https://github.com/DiegoMZD/StockForecasting.git
```
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Run the Jupyter notebooks in the notebooks/ directory to explore the analysis and modeling steps.
## Requirements
- Python 3.8+
- Required libraries (found in `requirements.txt`)
    - numpy
    - pandas
    - yfinance
    - matplotlib
    - seaborn
    - statsmodels
    - pmdarima
    - scikit-learn
    - xgboost
## License
This project is licensed under the MIT License. See the [LICENSE](https://github.com/DiegoMZD/StockForecasting/blob/main/LICENSE) file for details.