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


### 4. **Accuracy Calculation Script**
A separate script calculates the average MAPE across all SKU-Warehouse pairs and the model accuracy:
python
import pandas as pd

# Load the model error data from 'Model_Errors.csv'
error_df = pd.read_csv('Model_Errors.csv')

# Check if 'Error (MAPE)' column exists in the DataFrame
if 'Error (MAPE)' in error_df.columns:
    # Calculate the average MAPE
    average_mape = error_df['Error (MAPE)'].mean()

    # Calculate Accuracy
    accuracy = 100 - average_mape

    # Display MAPE and Accuracy
    print(f"Average MAPE: {average_mape:.2f}%")
    print(f"Accuracy: {accuracy:.2f}%")
else:
    print("Error: 'Error (MAPE)' column not found in the 'Model_Errors.csv' file.")
