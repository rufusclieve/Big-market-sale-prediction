# Big Market Sale Prediction

This project focuses on predicting the sales of various products in different outlets of a big market using machine learning models. The aim is to build a model that can accurately forecast sales based on several product and outlet features. The project uses the dataset available in CSV format, which includes product and store-level data.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Features](#features)
- [Target](#target)
- [Data Preprocessing](#data-preprocessing)
- [Modeling Techniques](#modeling-techniques)
- [Evaluation](#evaluation)
- [Results](#results)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Conclusion](#conclusion)

## Project Overview
The Big Market Sale Prediction project aims to predict the sales of items in different stores based on several features related to the items and the outlets. The primary goal is to develop a machine learning model that can generalize well on unseen data to accurately predict **Item Outlet Sales**.

## Dataset Description
The dataset contains 8523 records and 12 columns. It includes product attributes as well as store attributes. Below are the details of the columns in the dataset.

### Features:
1. **Item_Identifier**: Unique identifier for each item.
2. **Item_Weight**: The weight of the product.
3. **Item_Fat_Content**: Fat content of the product (e.g., Low Fat, Regular).
4. **Item_Visibility**: The proportion of display area allocated to the product.
5. **Item_Type**: The category to which the product belongs (e.g., Dairy, Soft Drinks, Fruits).
6. **Item_MRP**: Maximum Retail Price of the product.
7. **Outlet_Identifier**: Unique identifier for each store.
8. **Outlet_Establishment_Year**: The year when the outlet was established.
9. **Outlet_Size**: The size of the outlet (e.g., Small, Medium, Large).
10. **Outlet_Location_Type**: The type of location where the outlet is situated (e.g., Tier 1, Tier 2, Tier 3).
11. **Outlet_Type**: The type of the outlet (e.g., Grocery Store, Supermarket Type1).
   
### Target:
- **Item_Outlet_Sales**: The total sales of the product at a particular store.

## Data Preprocessing
1. **Handling Missing Values**:
   - Missing values in `Item_Weight` were imputed using the **mean** value of the column.
   - Missing values in `Outlet_Size` were imputed using the **mode** based on the `Outlet_Type`.

2. **Label Encoding**:
   - Categorical variables like `Item_Fat_Content`, `Item_Type`, `Outlet_Size`, `Outlet_Location_Type`, `Outlet_Type`, and `Outlet_Identifier` were label encoded.

3. **Splitting the Dataset**:
   - The data was split into **training** and **testing** sets with an 80-20 split using `train_test_split` from Scikit-learn.

## Modeling Techniques
The following machine learning algorithms were implemented:
1. **XGBoost Regressor**: An advanced implementation of gradient boosting used to handle large datasets and improve performance.
2. **Metrics Used**: 
   - **R-squared (R²)**: To measure the proportion of the variance in the dependent variable that is predictable from the independent variables.

## Evaluation
1. **Training Data**: After training the model, the R² score on the training data was **0.8762**, indicating a good fit for the training data.
2. **Testing Data**: The R² score on the test data was **0.5017**, which suggests some overfitting on the training data and leaves room for improvement.

## Results
- The **XGBoost Regressor** model achieved an **R² score of 0.876** on the training set and **0.501** on the test set.
- The model's performance was evaluated using standard regression metrics, and while the training data predictions were quite accurate, the performance on the test set showed room for further tuning and optimization.

## Requirements
To run this project, you will need the following dependencies:

- Python 3.x
- Libraries:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scikit-learn
  - xgboost

You can install the required packages using:
```bash
pip install -r requirements.txt
```

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/big-market-sale-prediction.git
   ```
2. Navigate to the project directory:
   ```bash
   cd big-market-sale-prediction
   ```
3. Open the **Jupyter Notebook** or **Google Colab** file and run the code.
4. Make sure to place the dataset (`Train.csv`) in the same directory as the notebook.

## Conclusion
The **Big Market Sale Prediction** project successfully predicted sales figures for various products across different outlets. The use of **XGBoost** provided good performance on the training data, though further tuning may be necessary to improve generalization on test data. The project demonstrates how machine learning techniques can be applied to solve real-world business problems like sales forecasting.
