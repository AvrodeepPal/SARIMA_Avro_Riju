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
```python

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

Installation and Usage
Prerequisites
Python 3.8 or higher
Required Python libraries:
pandas
numpy
matplotlib
seaborn
statsmodels
scikit-learn
Installation
Clone the repository:
bash
Always show details

Copy code
git clone https://github.com/your-username/sales-forecasting.git
cd sales-forecasting
Install dependencies:
bash
Always show details

Copy code
pip install -r requirements.txt
Usage
Place the input file Final.csv in the same directory as the script.

Run the main script:

bash
Always show details

Copy code
python main.py
Outputs will be saved as Submission.csv and Model_Errors.csv.

(Optional) Run the accuracy calculation script:

bash
Always show details

Copy code
python calculate_accuracy.py
Code Highlights
Forecasting Methodology
The SARIMA model is used for time series forecasting with seasonal adjustments.
Training data includes all sales up to May 2021.
Predictions are made for June 2021.
Error Metric
Mean Absolute Percentage Error (MAPE) is calculated for each SKU-Warehouse pair:
MAPE
=
1
𝑛
∑
𝑖
=
1
𝑛
∣
𝑦
𝑖
−
𝑦
^
𝑖
𝑦
𝑖
∣
×
100
MAPE= 
n
1
​
  
i=1
∑
n
​
  
​
  
y 
i
​
 
y 
i
​
 − 
y
^
​
  
i
​
 
​
  
​
 ×100
Results
Forecasts: The predicted sales for June 2021 are saved in Submission.csv.
Model Performance: The average MAPE and accuracy are calculated using the script provided.
Visualization Examples
Overall Sales Trends: A line plot showing sales trends for all warehouses.

Seasonal Decomposition: Seasonal, trend, and residual components of an example SKU-Warehouse time series.

Forecast vs. Actual: A line plot comparing actual sales and forecasted sales for an example SKU-Warehouse pair.

Future Improvements
Include hyperparameter tuning for SARIMA to optimize model performance.
Automate data validation for missing or incorrect values.
Add support for forecasting multiple future periods.
Integrate an interactive dashboard for visualizing forecasts and errors.
