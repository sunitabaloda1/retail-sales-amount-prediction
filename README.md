# Retail Sales Amount Prediction & Customer Spending Analysis

## Programme

**M.Sc. Data Science & Artificial Intelligence**

## Problem Statement

**P2 – Retail Sales Amount Prediction & Customer Spending Analysis**

## Development Platform

**Google Colaboratory (Google Colab)**

---

## 1. Project Overview

This project develops a machine learning solution capable of predicting retail invoice amounts using historical transaction data from the UCI Online Retail dataset.

The project follows a complete data science workflow, beginning with data exploration and cleaning, followed by feature engineering, model development, performance evaluation, and business interpretation.

The primary business objective is to assist retail organizations in improving:

- Sales forecasting
- Inventory planning
- Procurement planning
- Transaction-level prediction
- Data-driven business decision-making

The complete implementation is provided in the Jupyter/Google Colab notebook included in this repository.

---

## 2. Dataset

The project uses the **Online Retail dataset** from the **UCI Machine Learning Repository**
Ref- [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/352/online+retail).

The dataset contains transactional records from a UK-based online retailer and includes important variables such as:

- Invoice Number
- Stock Code
- Product Description
- Quantity
- Invoice Date
- Unit Price
- Customer ID
- Country

The original dataset contains more than 540,000 transactions representing customer purchases from multiple countries.

The dataset is **not stored directly in this GitHub repository**. It is referenced from the UCI Machine Learning Repository to keep the repository lightweight and avoid unnecessary duplication of the publicly available dataset.

**Dataset Source:** UCI Machine Learning Repository – Online Retail Dataset

---

## 3. Project Workflow

The project follows an end-to-end machine learning workflow:

1. Dataset loading and inspection
2. Data quality assessment
3. Missing-value analysis
4. Duplicate and invalid transaction handling
5. Exploratory Data Analysis (EDA)
6. Feature engineering
7. Train-test split
8. Regression model development
9. Hyperparameter tuning
10. Model comparison
11. Prediction diagnostics
12. Residual analysis
13. Feature importance analysis
14. Business interpretation
15. Recommendations and limitations

The complete workflow is implemented in:

`notebook/Retail_Sales_Amount_Prediction.ipynb`

---

## 4. Week 5 Feedback Implementation

The project was enhanced based on the Week 5 reviewer feedback.

The following improvements were incorporated:

- Comprehensive Exploratory Data Analysis
- Detailed data cleaning and preprocessing
- Temporal feature engineering
- Multiple regression models for comparison
- Hyperparameter tuning using GridSearchCV
- Actual vs Predicted visualization
- Residual analysis
- Feature Importance analysis using Random Forest
- Business recommendations
- Project limitations
- Improved markdown explanations and documentation throughout the notebook

These improvements strengthened the technical completeness and presentation of the machine learning workflow.

---

## 5. Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the structure, distribution, relationships, and business characteristics of the transaction data before model development.

### Key Observations

- Most transactions originated from the United Kingdom.
- Invoice Amount displayed a highly right-skewed distribution.
- A small number of transactions represented exceptionally large purchases.
- Sales activity increased noticeably during the final quarter of the year.
- Quantity showed the strongest relationship with Invoice Amount.
- Unit Price also contributed positively to Invoice Amount.
- Most temporal features showed comparatively weaker relationships with the target variable.

### EDA Visualizations

The notebook includes analysis and visualizations covering:

- Quantity distribution
- Unit Price distribution
- Monthly sales trend
- Invoice Amount distribution
- Log-transformed Invoice Amount
- Correlation heatmap

These visualizations provide insight into transaction behaviour, feature relationships, skewness, and seasonal patterns.

---

## 6. Data Preparation

Several preprocessing steps were applied before model development.

The data preparation process included:

- Removal of records with missing Customer IDs
- Removal of cancelled transactions
- Removal of records with zero or negative Quantity
- Removal of records with zero or negative Unit Price
- Creation of `InvoiceAmount` as the target variable
- Handling of invalid observations
- Preparation of a clean dataset for predictive modelling

This process ensured that invalid and unsuitable transaction records did not adversely affect the predictive modelling stage.

---

## 7. Feature Engineering

Additional variables were created from `Invoice Date` to allow the models to capture temporal and seasonal purchasing behaviour.

The engineered features included:

- Invoice Year
- Invoice Month
- Invoice Day
- Invoice Weekday
- Invoice Hour
- Quarter
- Weekend Indicator

Feature engineering enabled the models to incorporate temporal information beyond the original transaction attributes.

---

## 8. Machine Learning Models

Three regression models were developed and compared.

### 8.1 Linear Regression

Linear Regression was used as the baseline model.

It achieved the strongest overall coefficient of determination (R²) among the evaluated models, demonstrating strong predictive performance and good generalization on the cleaned dataset.

### 8.2 Decision Tree Regressor

A Decision Tree Regressor was developed to capture non-linear relationships between the transaction features and Invoice Amount.

The model produced a very low Mean Absolute Error (MAE), indicating accurate predictions for many transactions.

Hyperparameter tuning using GridSearchCV identified an optimal maximum tree depth of **10**.

The tuned model produced performance similar to the untuned model, suggesting that the original configuration was already close to optimal.

### 8.3 Random Forest Regressor

A Random Forest Regressor was developed to investigate whether an ensemble learning approach could improve predictive performance.

Although Random Forest reduced some prediction variability, it produced lower overall predictive performance than Linear Regression for this dataset.

This demonstrates that more complex models do not necessarily outperform simpler algorithms when the underlying data characteristics favour simpler relationships.

---

## 9. Model Evaluation

The models were evaluated using three primary regression metrics:

- **R² Score**
- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**

### Interpretation

**R² Score** measures the proportion of variance in the target variable explained by the model.

**MAE** measures the average absolute difference between actual and predicted invoice amounts.

**RMSE** measures prediction error while giving greater weight to larger errors.

The notebook provides a performance comparison of the evaluated regression models using these metrics.

---

## 10. Model Comparison

The model comparison demonstrated that model complexity does not automatically translate into better predictive performance.

### Overall Findings

- Linear Regression achieved the strongest overall R² performance.
- Decision Tree provided competitive transaction-level accuracy.
- Random Forest did not outperform the simpler Linear Regression model.
- The Decision Tree hyperparameter tuning produced performance similar to the untuned configuration.
- The results indicate that the relationship between the major transaction variables and Invoice Amount can be captured effectively by a relatively simple model.

The comparison highlights the importance of evaluating models empirically rather than assuming that more complex algorithms will always perform better.

---

## 11. Hyperparameter Tuning

Hyperparameter tuning was performed using **GridSearchCV**.

For the Decision Tree model, tuning identified:

**Maximum tree depth = 10**

The tuned model showed performance similar to the original model, indicating that the initial model configuration was already reasonably close to an effective solution.

Hyperparameter tuning therefore provided additional evidence supporting the selected model configuration.

---

## 12. Prediction and Error Analysis

The project includes visual diagnostics to investigate prediction behaviour and model errors.

The analysis includes:

- Actual vs Predicted Plot
- Residual Plot
- Zoomed Residual Plot

### Key Findings

- Most low- and medium-value invoices were predicted relatively accurately.
- Extremely large invoices were more difficult to predict.
- Residuals were generally centred around zero.
- Prediction error increased for high-value transactions.
- The highly skewed distribution of Invoice Amount contributed to larger errors for extreme transactions.

This error analysis provides additional insight beyond numerical evaluation metrics and helps explain where the models perform well and where prediction uncertainty remains higher.

---

## 13. Feature Importance Analysis

Feature Importance analysis was performed using the Random Forest model.

The analysis showed that:

1. **Quantity** was the most influential predictor of Invoice Amount.
2. **Unit Price** was the second most important predictor.
3. Temporal variables such as Month, Day, Hour, Quarter, and Weekend contributed relatively little to predictive performance.

These findings were consistent with the correlation analysis performed during EDA.

The results indicate that transaction-level characteristics, particularly the quantity purchased and unit price, are the primary drivers of invoice value in this dataset.

---

## 14. Business Recommendations

Based on the findings, the following business recommendations were identified:

### Inventory Planning

Retailers can use transaction-level sales predictions to improve inventory planning, particularly before periods of increased seasonal demand.

### High-Volume Product Availability

Products associated with high transaction quantities should be monitored closely to reduce the risk of stock shortages.

### Sales Forecasting

Predictive modelling can support sales forecasting and provide an additional quantitative input for business planning.

### Procurement Planning

Predicted transaction values can assist procurement teams in planning purchasing requirements and allocating resources.

### Large Transaction Monitoring

Unusually large transactions should be monitored separately because they can have a significant influence on overall sales performance and prediction error.

### Data Quality

Maintaining accurate customer and transaction information is important for improving the reliability of predictive analytics.

---

## 15. Project Limitations

The project has several limitations:

- The dataset represents a single online retailer and may not generalize to all retail businesses.
- External business factors such as promotions, holidays, marketing campaigns, and competitor pricing were unavailable.
- Invoice Amount exhibits a highly skewed distribution with extreme values.
- Customer demographic information was unavailable.
- The current feature engineering approach primarily focuses on temporal variables.
- Additional feature engineering and advanced machine learning models may further improve predictive performance.
- Cross-validation and more systematic generalization analysis could provide more reliable estimates of model performance.

---

## 16. Future Improvements

Several extensions could further strengthen the project:

- Explore advanced regression models such as Gradient Boosting and other ensemble methods.
- Perform more systematic hyperparameter optimization.
- Introduce cross-validation for more robust model evaluation.
- Develop additional behavioural and transaction-level features.
- Investigate transformations for the highly skewed target variable.
- Perform deeper analysis of extreme-value transactions.
- Compare model performance across different customer or product segments.
- Incorporate additional business variables such as promotions, holidays, and external market factors when available.

---

## 17. Overall Results and Conclusion

This project successfully implements a complete end-to-end machine learning workflow for retail sales amount prediction using the UCI Online Retail dataset.

The project incorporates:

- Data inspection
- Data cleaning
- Exploratory Data Analysis
- Feature engineering
- Regression modelling
- Hyperparameter tuning
- Model comparison
- Prediction diagnostics
- Residual analysis
- Feature importance analysis
- Business interpretation
- Recommendations
- Limitations and future improvements

Among the evaluated models, **Linear Regression demonstrated the strongest overall predictive performance**, while the Decision Tree provided competitive accuracy for individual transactions.

Feature importance analysis confirmed that **Quantity and Unit Price were the primary drivers of Invoice Amount**.

The analysis also demonstrated that extremely large transactions remain more difficult to predict because of the highly skewed nature of the target variable.

Overall, the project demonstrates how machine learning can be applied to retail transaction data to support sales forecasting, inventory planning, procurement decisions, and data-driven business decision-making.

---

## 18. Notebook

The complete executable implementation, analysis, visualizations, model development, evaluation, and conclusions are available in the project notebook:

**`notebook/Retail_Sales_Amount_Prediction.ipynb`**

The notebook was developed using **Google Colaboratory (Google Colab)**.

---

## 19. Repository Structure

```text
retail-sales-amount-prediction/
│
├── .gitignore
├── README.md
├── requirements.txt
│
└── notebook/
    ├── .gitkeep
    └── Retail_Sales_Amount_Prediction.ipynb

## Technologies Used

- Python
- Google Colaboratory
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- GridSearchCV
- Regression Modelling
- Exploratory Data Analysis
- Data Visualization



## Author

Sunita Baloda
