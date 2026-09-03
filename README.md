# Retail Sales Amount Prediction & Customer Spending Analysis

## Programme
M.Sc. Data Science & Artificial Intelligence

## Problem Statement
P2 – Retail Sales Amount Prediction & Customer Spending Analysis

## Project Overview

This project develops a machine learning solution for predicting retail invoice amounts using historical transaction data from the UCI Online Retail dataset.

The project follows an end-to-end data science workflow including:

- Data exploration and cleaning
- Exploratory Data Analysis (EDA)
- Feature engineering
- Regression model development
- Hyperparameter tuning
- Model evaluation
- Prediction error analysis
- Feature importance analysis
- Business interpretation

The primary business objective is to support retail sales forecasting, inventory planning, and data-driven decision-making.

## Dataset

The dataset used in this project is the **Online Retail dataset** from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail). The dataset contains 541,909 transactional records from a UK-based online retailer covering transactions from December 2010 to December 2011.

The dataset includes variables such as:

- Invoice Number
- Stock Code
- Product Description
- Quantity
- Invoice Date
- Unit Price
- Customer ID
- Country

The dataset is referenced from the UCI Machine Learning Repository rather than being stored directly in this GitHub repository.

## Notebook

The complete analysis and machine learning implementation are available in:

`notebook/Retail_Sales_Amount_Prediction.ipynb`

The notebook contains the complete workflow from data preparation through model evaluation and business recommendations.

## Machine Learning Models

The following regression models were implemented and compared:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor

Hyperparameter tuning was also performed using GridSearchCV.

## Model Evaluation

Models were evaluated using:

- R² Score
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

Additional diagnostic analysis included:

- Actual vs Predicted visualization
- Residual analysis
- Feature importance analysis

## Key Findings

The analysis showed that:

- Quantity was the most influential predictor of Invoice Amount.
- Unit Price was the second most important predictor.
- Invoice Amount was highly right-skewed.
- Most low- and medium-value transactions were predicted relatively accurately.
- Extremely large invoices remained more difficult to predict.
- Linear Regression demonstrated the strongest overall predictive performance among the evaluated models.

## Business Recommendations

The findings can support:

- Inventory planning before seasonal demand increases
- Availability planning for high-volume products
- Sales forecasting and procurement planning
- Separate monitoring of unusually large transactions
- Improved transaction and customer data quality

## Limitations

The project has several limitations:

- The dataset represents a single online retailer.
- External factors such as promotions, holidays, and competitor pricing were unavailable.
- Invoice Amount contains extreme values and is highly skewed.
- Customer demographic information is unavailable.
- Additional feature engineering and advanced models may further improve prediction performance.

## Development Platform

Google Colaboratory (Google Colab)

## Author

Sunita Baloda
