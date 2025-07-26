# Churn Analysis EDA

This repository contains a Jupyter Notebook (`Churn_Analysis_EDA1.ipynb`) that performs Exploratory Data Analysis (EDA) on a customer churn dataset. The goal of this analysis is to understand the factors contributing to customer churn.

## Dataset

The dataset used in this analysis is named `CustomerChurn.csv`. It contains customer data, including information about services subscribed, monthly charges, tenure, and whether the customer has churned (left the company) in the last month.

## Notebook Contents

The Jupyter Notebook `Churn_Analysis_EDA1.ipynb` covers the following steps:

### 1. Introduction
*   **Churn Analysis**: Overview of the project's objective.
*   **Dataset Info**: Provides a brief description of the dataset.

### 2. Setup and Data Loading
*   **Import Libraries**: Imports necessary Python libraries such as `numpy`, `pandas`, `seaborn`, and `matplotlib.pyplot`.
*   **Load Data File**: Loads the `CustomerChurn.csv` file into a pandas DataFrame.

### 3. Initial Data Inspection
*   **View Top Records**: Displays the first 5 rows of the dataset to get a quick overview of the data structure.
*   **Check Data Attributes**:
    *   `telco_base_data.shape`: Shows the number of rows and columns in the dataset.
    *   `telco_base_data.columns.values`: Lists all column names.
    *   `telco_base_data.dtypes`: Displays the data types of each column.
    *   `telco_base_data.describe()`: Provides descriptive statistics for numerical columns.
*   **Target Variable Analysis**:
    *   Visualizes the distribution of the `Churn` variable using a horizontal bar plot.
    *   Calculates the percentage and count of churned vs. non-churned customers, revealing data imbalance.

### 4. Data Cleaning
*   **Create a Copy**: A copy of the base data (`telco_base_data`) is made for manipulation to preserve the original dataset.
*   **Convert `TotalCharges` to Numeric**: The `TotalCharges` column is converted from `object` to a numeric data type. The `errors='coerce'` argument is used to convert non-numeric values into `NaN` (Not a Number).
*   **Handle Missing Values**:
    *   Missing values in `TotalCharges` are identified (11 missing values found).
    *   Since the percentage of missing values is very low (0.15%), these rows are dropped from the dataset.
*   **Create `tenure_group`**: The `tenure` variable is grouped into bins of 12 months (e.g., '1 - 12', '13 - 24', etc.) to create a new categorical variable `tenure_group`.
*   **Drop Unnecessary Columns**: The `customerID` and original `tenure` columns are dropped as they are not required for further analysis or have been transformed.

### 5. Data Exploration (Univariate Analysis)
*   **Missing Data Visualization**: A point plot is generated to visualize the percentage of missing values across all columns (after initial cleaning, it shows no missing values).
*   **Univariate Analysis of Predictors**: The notebook prepares for univariate analysis by plotting distributions of individual predictors against the `Churn` variable.


## Analysis Summary

The EDA reveals that the dataset is imbalanced, with a significantly higher number of non-churned customers compared to churned customers (approximately 73% vs. 27%). This imbalance will need to be addressed in subsequent modeling steps. The data cleaning process involved converting `TotalCharges` to a numeric type and handling a small number of missing values by dropping the corresponding rows. A new `tenure_group` feature was created to categorize customer tenure.

Further analysis will delve deeper into the relationships between individual features and customer churn.
