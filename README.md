# Fare-Forecasting-in-Quahog-City

## About the Project:
RideWave, a versatile urban mobility service, has been operating in Quahog City for the past five years. The company offers three types of vehicles: bikes, autos (three-wheeled vehicles), and cars. As they face increasing competition, RideWave wants to leverage its historical data to optimize pricing strategies for each vehicle type in Quahog City.

RideWave has a rich dataset containing hourly data from 2021 to 2023 for bikes, autos and cars from RideWave. I analyzed the provided data, developed predictive models for fare forecasting, and provided actionable insights to help RideWave implement dynamic pricing across its multi-vehicle fleet in Quahog City.

## Evaluation Metric:
**Symmetric Mean Absolute Percentage Error (SMAPE)**

The Symmetric Mean Absolute Percentage Error (SMAPE) is calculated as:
```python
smape = np.mean(np.abs(y_pred - y_true) / (np.abs(y_pred) + np.abs(y_true)))
```

Lower the score, the better you are!

SMAPE will be calculated based on all 3 columns in the submission:
- average_fare_bike
- average_fare_auto
- average_fare_car

## Methodology Used:

1. **Data Exploration and Preparation**:
   - Checked for null columns and duplicate rows.
   - Visualized data using BoxPlot, Violin Plot, HeatMap, Correlation Matrix, LinePlot and Histogram.
   - Checked for outliers using the IQR method.

2. **Time Series Characterization**:
   - Created 3 separate DataFrames for each vehicle type, and visualized and summarized it using boxplots.
   - Plotted average fares for all vehicle types.
   - Applied Holt and Holt-Winter's Method for forecasting and plotted them both for all the vehicle types to compare them.

3. **Advanced Forecasting and Feature Engineering**:
   - Applied the SARIMAX Model for each of the vehicle types for Time Series Forecasting, since it can capture both trends and seasonality.
   - Performed Feature Engineering on the 3 dataframes to add new features for improved analysis.
   - Tested the feature engineering new features using XGBoost Model.

4. **Ensemble Modeling and Pricing Strategy**:
   - Applied SARIMAX model for bikes, XGBoost model for autos and VAR model for cars.
   - Applied Ensemble Model to combine all these models to create a more reliable and final model.
