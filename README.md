# Data Preprocessing Workflow

This document outlines the data preprocessing steps I followed to prepare the dataset for analysis and modeling. Below is a detailed breakdown of each step in the process.

## 1. Inspecting the Data
Before starting with any preprocessing, I inspected the dataset to understand its structure, features, and potential issues such as missing values, inconsistent data, and duplicates. This includes:
- Checking the first few rows of the dataset (`head()`).
- Verifying the data types of each column.
- Checking for missing values and duplicates.

## 2. Data Cleaning
### a. Handling Missing Values
- Identified missing values using `isnull()` and `info()` functions.
- For columns with missing data, appropriate strategies were applied:
  - **Numerical columns**: Missing values were filled with the median or mean.
  - **Categorical columns**: Missing values were replaced with the most frequent category.
  - In some cases, rows with missing data were removed if they contributed little to the overall dataset.

### b. Checking and Removing Duplicates
- Inspected for duplicates across various dataframes such as transactions, customer demographics, and product information using `duplicated()`.
- Removed duplicates to ensure the data remained clean and free from redundancy.

### c. Correcting Data Types
- Ensured that columns had appropriate data types. For instance:
  - Dates (`InvoiceDate`) were converted from string to `datetime`.
  - Numeric values stored as strings were converted to integers or floats.

## 3. Handling Outliers
- Detected outliers in numerical columns like `Quantity` and `Price` using statistical methods like the Interquartile Range (IQR).
- Removed or capped extreme values to prevent skewness in the data and improve model performance.

## 4. Data Integration
- Integrated data from multiple sources such as transactional datasets (`trans_1` and `trans_2`), customer demographics, and product information into a single consolidated dataset using joins (e.g., `merge()`).
- Ensured the consistency of key identifiers across datasets before merging (e.g., `Customer ID`, `StockCode`).

## 5. Handling Inconsistent Data
- Fixed inconsistencies in data entries, such as correcting misspelled or misformatted values in categorical columns (e.g., `Country`, `StockCode`).
- Standardized categorical data to ensure consistency across the dataset.

## 6. Data Validation
- After cleaning, I validated the dataset by checking its structure and content once again.
  - Ensured there were no remaining missing values, duplicates, or outliers.
  - Confirmed that the data was in the correct format and ready for analysis.
