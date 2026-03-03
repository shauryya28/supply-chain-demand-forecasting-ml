#  Supply Chain Demand Forecasting Using Machine Learning

##  Project Overview

This project builds a machine learning model to forecast product demand in a fashion and beauty supply chain environment. Accurate demand prediction helps reduce stockouts, overstocking, and operational inefficiencies by enabling data-driven decisions across inventory, production, and logistics.

The objective was to predict **units sold** using historical supply chain and business metrics while identifying the most influential features driving demand.

---

##  Business Problem

Supply chain demand forecasting is influenced by multiple operational and financial factors such as:

- Inventory levels  
- Product pricing  
- Manufacturing costs  
- Shipping schedules and carriers  
- Lead times  
- Promotional activity  

The challenge was to:

- Identify the most predictive features  
- Compare multiple machine learning algorithms  
- Build a highly accurate yet interpretable model  
- Ensure robustness across different feature sets  

---

##  Dataset

The dataset (`supply_chain_data.csv`) includes historical operational and financial metrics such as:

- Product type  
- Stock levels  
- Lead times  
- Shipping carriers  
- Product price  
- Availability  
- Cost-related variables  
- Revenue-related variables  

###  Feature Engineering

Additional business-driven features were engineered:

- `Profit_margin`  
- `Cost_per_unit`  
- `Revenue_per_unit`  
- Time-based features extracted from a synthetic Date column  

---

##  Methodology

### 1. Data Preprocessing

- One-hot encoding for categorical variables  
- Handling missing values  
- Feature scaling using Standardization  
- Time-based feature extraction  
- Business-centric feature engineering  

---

### 2. Feature Selection

Two feature selection strategies were applied:

#### A. SelectKBest (Univariate Regression)
- Selected top 20 statistically relevant features  

#### B. Random Forest Feature Importance
Identified the top 3 most predictive features:

- **Stock levels**
- **Shipping carriers**
- **Cost_per_unit**

---

### 3. Models Implemented

All models were trained using an 80/20 train-test split.

- Random Forest Regressor (Default)
- Random Forest (GridSearchCV Tuned)
- Random Forest (RandomizedSearchCV Tuned)
- Neural Network (MLP Regressor)
- XGBoost Regressor

---

##  Results

### 🏆 Best Performing Model  
**Random Forest Regressor (Top 3 Features)**

| Metric | Value |
|--------|--------|
| R² Score | **0.84** |
| RMSE | **104.51** |
| MSE | 10,922.61 |

###  Model Comparison

- MLP Regressor → R² = 0.37  
- RandomizedSearchCV RF → R² = 0.67  
- GridSearchCV RF → R² = 0.65  
- XGBoost → R² = 0.60  

###  Key Insight

A simple Random Forest trained on only three high-importance features outperformed more complex models and larger feature sets, demonstrating that **strong feature selection and interpretability can outperform model complexity**.

---

##  Model Evaluation

The following visualizations were used to validate performance:

- Actual vs Predicted Sales Plot  
- Residual Plot  
- Feature Importance Plot  

The residual distribution showed no major bias, and predictions aligned closely with actual values.

---

##  Tech Stack

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- XGBoost  
- Matplotlib  
- Seaborn  

