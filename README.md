# Wind Speed Analysis using ARIMA and GARCH Models

## Overview
This project focuses on analyzing wind speed data, identifying trends, and forecasting future values using ARIMA and GARCH models. The analysis includes:
- Data preprocessing and visualization
- Stationarity testing using the Augmented Dickey-Fuller (ADF) test
- Seasonal decomposition of time series
- Model building and evaluation for ARIMA and GARCH
- Wind speed forecasting using ARIMA

## Dataset
The dataset contains historical wind speed data, indexed by date. The primary column used in the analysis is:
- `wind_speed`: Wind speed measurements over time

## Code Workflow
1. **Data Preprocessing:**
   - Handling missing values
   - Converting date column to datetime format
   - Setting date as index and defining frequency

2. **Exploratory Data Analysis (EDA):**
   - Time series visualization
   - Seasonal decomposition
   - Checking for stationarity using ADF test
   
3. **Modeling:**
   - ARIMA model for forecasting
   - GARCH model for volatility estimation

4. **Forecasting:**
   - Forecasting wind speed using ARIMA
   - Visualizing forecast with confidence intervals

## Key Findings
- **Seasonal Trends:** The data exhibits seasonal patterns with regular peaks and troughs.
- **Trend Analysis:** The trend indicates a gradual change, with an initial decline followed by an increase towards the end of the period.
- **Outliers:** Observed in the residuals, indicating rare but strong anomalies in wind speed changes.
- **Stationarity Test:**
  - ADF Statistic: `-3.8381`
  - p-value: `0.0025`
  - Conclusion: The time series is stationary, allowing further modeling.
- **GARCH Model Results:**
  - The average wind speed change is around `3.62 km/h`.
  - GARCH parameters for significant changes were found to be insignificant, making the model unsuitable.
- **ARIMA Model Results:**
  - Wind speed data is dependent on previous values.
  - Model parameters were found to be significant.
  - ARIMA effectively captures wind speed patterns.
- **Forecast Interpretation:**
  - The forecast suggests that wind speed will remain relatively stable in the future.
  - However, long-term accuracy may be affected by missing external factors like weather conditions.

## Outputs
Here is a comparison of actual vs predicted wind speed values:

| Date       | Actual Wind Speed (kmph) | Forecasted Wind Speed (kmph) |
|------------|--------------------------|------------------------------|
| 2023-01-01 | 14.25                     | 14.10                        |
| 2023-01-02 | 13.40                     | 13.30                        |
| 2023-01-03 | 15.60                     | 15.50                        |
| ...        | ...                        | ...                          |
| 2023-01-11 | NaN                        | 15.60                        |

## Conclusion
- **GARCH was not suitable** due to insignificant parameters affecting variations in wind speed.
- **ARIMA effectively modeled** the dependence on past values, making it the preferred choice.
- **For better accuracy**, incorporating additional factors like seasonal weather changes would be beneficial.

## Running the Code
To execute the analysis, install the required dependencies and run the script:
```bash
pip install numpy pandas matplotlib seaborn arch statsmodels
python wind_speed_analysis.py
```

## License
This project is open-source and available under the MIT License.

