# Sales Forecasting and Error Analysis Project

## Overview

This project demonstrates the implementation of a time series forecasting model to predict sales for various SKUs (Stock Keeping Units) across different warehouses. It includes data preprocessing, exploratory data analysis, SARIMA model forecasting, and error analysis to measure model performance.

The outputs include:
- Predicted sales for June 2021 saved in a file named `Submission.csv`.
- Model error metrics saved in `Model_Errors.csv`.

## Project Objectives
1. **Sales Prediction**: Forecast sales for each SKU-Warehouse combination for June 2021.
2. **Error Analysis**: Measure the performance of the model using the Mean Absolute Percentage Error (MAPE) metric.
3. **Visualization**: Visualize sales trends and decomposition of seasonal patterns.
4. **Documentation**: Save results in structured formats for further analysis.

---

## Files and Directories

### 1. **Main Code File**
The main Python script performs:
- Data preprocessing
- Sales trend visualization
- Seasonal decomposition
- SARIMA forecasting for each SKU-Warehouse pair
- Generation of two output files:
  - `Submission.csv`: Contains the forecasted sales for June 2021.
  - `Model_Errors.csv`: Contains the MAPE error for each SKU-Warehouse combination.

### 2. **Output Files**
- **Submission.csv**: Forecasted sales with the following columns:
  - `Warehouse id`: ID of the warehouse.
  - `Region`: Region of the warehouse.
  - `SKU id`: ID of the SKU.
  - `Jun-21`: Forecasted sales for June 2021.

- **Model_Errors.csv**: Error metrics with the following columns:
  - `Warehouse id`: ID of the warehouse.
  - `Region`: Region of the warehouse.
  - `SKU id`: ID of the SKU.
  - `Error (MAPE)`: Mean Absolute Percentage Error for the model.

### 3. **Visualization Code**
The script includes visualizations:
- Overall sales trends by warehouse.
- Seasonal decomposition for a specific SKU-Warehouse pair.
- Comparison of actual and forecasted sales for one SKU-Warehouse pair.

