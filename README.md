# Churn Prediction Project

## Aim
The objective of this project is to develop a comprehensive solution for predicting customer churn. It involves a systematic approach that includes exploratory data analysis, data preprocessing, model building, and performance evaluation. The goal is to extract actionable insights from customer data, build effective machine learning models for churn prediction, and communicate the findings to both technical and non-technical stakeholders. Ultimately, this project aims to support business strategies by identifying at-risk customers and providing recommendations to improve retention and reduce churn.

---

## Part 1: Exploratory Data Analysis (EDA)
The goal of this part is to conduct an exploratory data analysis (EDA) on the customer dataset to uncover patterns, relationships, and insights that will inform predictive modelling efforts. EDA is crucial for understanding the data and lays the groundwork for informed decision-making.

### 1. Overview of the Dataset
The dataset consists of 4,661 customer records and 18 features, including customer demographics, transaction behaviors, and customer service interactions. The initial analysis revealed:

- **Descriptive Statistics:**
  - `CustomerID`: Ranges from 50001 to 55630.
  - `Tenure`: Average tenure of approximately 10 months, with a minimum of 0 and a maximum of 61 months.
  - `Satisfaction Score`: Mean score of 3.07, indicating moderate customer satisfaction.

### 2. Handling Missing Values
Before deeper analyses, missing values were addressed:

- **Missing Data Overview:** 
  - The `Churn` column had 27 missing entries (0.58% of the dataset), which were removed to maintain the integrity of the analysis.
  - Other features were examined for missing values and handled accordingly.

### 3. Feature Distribution Analysis
Understanding feature distributions helps identify potential anomalies and patterns:

- **Tenure**: Right-skewed distribution, indicating that most customers have been with the company for a shorter duration.
- **Satisfaction Score**: Relatively normal distribution, though many customers rated their satisfaction low, prompting further investigation.
- **Churn**: Displayed class imbalance (83.3% retained vs. 16.7% churned), highlighting the need for strategies to address this during modeling.

### 4. Correlation Analysis
Correlation analysis was conducted to understand relationships between variables, visualized through a heatmap:

- **Positive Correlations:**
  - `Satisfaction Score` positively correlated with `Engagement Score` and `Recency Score`.
  - `Hour Spend on App` correlated positively with both `Order Count` and `Cashback Amount`.

- **Negative Correlations:**
  - Strong negative correlation between `Churn` and `Satisfaction Score`.
  - `Churn` also negatively correlated with `Engagement Score`.

### 5. Categorical Feature Analysis
Insights were gained from categorical features such as `Preferred Login Device`, `City Tier`, and `Preferred Payment Mode`:

- **Preferred Login Device**: Most customers preferred using Mobile Phones (around 49%).
- **City Tier**: A majority belonged to City Tier 1 (approximately 35%).
- **Preferred Payment Mode**: Debit Card was the most common payment method, used by 41% of customers.

### 6. Insights and Implications
- **Understanding Churn Drivers:** Key features influencing customer churn include satisfaction and engagement.
- **Targeted Marketing Opportunities:** Preferred login devices and payment methods can guide marketing strategies.
- **Customer Segmentation:** Tenure and satisfaction levels help in customer segmentation for retention strategies.

### Conclusion
The exploratory data analysis provided crucial insights into customer behaviors and characteristics, laying the foundation for the subsequent churn prediction model. Strategies aimed at enhancing customer satisfaction and retention can be developed from this analysis.

---

## Part 2: Churn Prediction
The objective of this part was to develop a machine learning model to predict whether a customer is likely to churn based on various customer features. This involved data preparation, model selection, and performance evaluation, aimed at providing insights for enhancing customer retention strategies.

### 1. Data Preparation
To ensure a robust model, several data preparation steps were undertaken:

- **Handling Missing Data:** Missing values were managed using imputation. Continuous features were filled with the median, and categorical features with the mode.
- **Feature Encoding:** Categorical variables were one-hot encoded, including features like `Preferred Payment Mode` and `Preferred Login Device`.
- **Scaling Features:** Continuous features like `Tenure` and `Cashback Amount` were scaled to ensure balanced contributions to the model.
- **Class Imbalance Management:** SMOTE (Synthetic Minority Over-sampling Technique) was applied, resulting in a balanced class distribution.

### 2. Model Selection and Training
Three machine learning algorithms were evaluated for churn prediction:

- **Logistic Regression:** 
  - Served as the baseline model.
  - Features were selected using Recursive Feature Elimination with Cross-Validation (RFECV).

- **Random Forest:** 
  - This ensemble method improved accuracy by aggregating decision trees and offered insights into feature importance.

- **XGBoost:** 
  - Known for speed and accuracy with complex datasets.
  - Optimized using RFECV.

### 3. Performance Evaluation
The models were assessed using a hold-out test set, yielding the following results:

- **Logistic Regression:**
  - Accuracy: 84%
  - ROC AUC Score: 0.85
  - **Key Features:** Satisfaction Score, Tenure, Complaints.

- **Random Forest:**
  - Accuracy: 93%
  - ROC AUC Score: 0.95
  - **Key Features:** Satisfaction Score, Complaints.

- **XGBoost:**
  - Accuracy: 93%
  - ROC AUC Score: 0.94
  - **Key Features:** Complaints, Tenure, Satisfaction Score.

### 4. Insights and Actionable Recommendations
- **Key Predictors of Churn:** Customer complaints, satisfaction scores, and tenure were the most significant factors.
- **Actionable Strategies:**
  - **Enhance Customer Support:** Address complaints to boost satisfaction and reduce churn.
  - **Targeted Engagement Initiatives:** Implement personalized marketing for dissatisfied customers.
  - **Incentives for Longer Tenure:** Introduce loyalty programs for long-term retention.

### Conclusion
The churn prediction model highlights factors leading to customer attrition. By focusing on key indicators and implementing tailored strategies, we can enhance customer loyalty and improve retention rates, leading to greater profitability and long-term success.
