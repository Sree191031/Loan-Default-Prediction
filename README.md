# Loan Default Prediction 

**Project Overview**  

The **Loan Default Prediction Project** leverages machine learning to predict loan defaults, enabling financial institutions to identify high-risk borrowers and mitigate financial risks. The project uses a dataset from Kaggle that contains borrower demographics, financial metrics, and loan details. By analyzing these factors, the project provides actionable insights to improve lending decisions.

---

### Data Overview 

**Dataset Details**  
- **Source**: [Loan Default Data](https://www.kaggle.com/datasets/nikhil1e9/loan-default/data)  
- **Rows**:  255,347   
- **Features**: 20  
- **Key Features**:
  - **Demographics**: Age, Income, Employment Length  
  - **Loan Details**: Loan Amount, Interest Rate, Loan Term  
  - **Behavioral Metrics**: Credit Score, Payment History  
  - **Target Variable**: Loan Default (0 = Non-default, 1 = Default)

**Data Quality**  
- Missing values handled using mean imputation.  
- Outliers in Loan Amount and Income capped at the 99th percentile.  

**Data Types**  
- Numerical: Loan Amount, Income, Credit Score  
- Categorical: Employment Status, Loan Purpose  
- Binary: Default Status  

---

### Methodology  

1. **Exploratory Data Analysis (EDA)**:  
   - Identified relationships between features, e.g., Credit Score and Default Rate (-0.78 correlation).  
   - Visualized trends by income bracket and employment status.

2. **Feature Engineering**:  
   - Added derived features like Debt-to-Income Ratio (DTI).  
   - Encoded categorical variables using one-hot encoding.  
   - Normalized numerical features for uniformity.

3. **Train-Test Split**:  
   - Split data into 80% training and 20% testing subsets.

4. **Model Selection and Hyperparameter Tuning**:  
   - Evaluated six classifiers: Decision Tree, Random Forest, Logistic Regression, k-NN, Naive Bayes, XGBoost.  
   - Optimized hyperparameters using **GridSearchCV**.

---

### Results Analysis  

| **Model**              | **Accuracy** | **Precision** | **Recall** | **ROC AUC** | **F1 Score** |  
|------------------------|--------------|---------------|------------|-------------|--------------|  
| Decision Tree          | 75%          | 26%           | 41%        | 0.69        | 32%          |  
| Random Forest          | 79%          | 48%           | 39%        | 0.74        | 43%          |  
| Logistic Regression    | 86%          | 70%           | 8%         | 0.82        | 14%          |  
| k-NN                   | 68%          | 22%           | 35%        | 0.61        | 27%          |  
| Naive Bayes            | 72%          | 20%           | 51%        | 0.63        | 29%          |  
| XGBoost                | 77%          | 51%           | 45%        | 0.78        | 48%          |  

### Insights  

1. **Best Performing Models**:  
   - **XGBoost**: Balanced performance across metrics.  
   - **Random Forest**: Reliable accuracy with good generalization.  

2. **Feature Importance**:  
   - Credit Score, Loan Amount, and Debt-to-Income Ratio are key predictors.  

3. **Metric Trade-offs**:  
   - High recall models (Naive Bayes) are ideal for identifying defaulters.  
   - High precision models (Logistic Regression) reduce false positives.

---

### Recommendations  

1. **Adopt XGBoost for Lending Decisions**: Its balanced performance ensures robust predictions.  
2. **Refine Loan Approval Criteria**: Focus on applicants with strong credit scores and manageable DTI ratios.  
3. **Implement Early Warning Systems**: Proactively monitor high-risk loans and offer repayment assistance.  
4. **Enhance Customer Segmentation**: Tailor loan products based on demographic and behavioral insights.  
5. **Regular Model Updates**: Continuously retrain models with new data for sustained accuracy.

---

### Summary  

This project demonstrates how machine learning can be effectively applied to loan risk assessment. Models like XGBoost and Random Forest offer reliable predictions, helping financial institutions optimize lending strategies, minimize defaults, and enhance profitability.
