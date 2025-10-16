<img width="474" height="478" alt="image" src="https://github.com/user-attachments/assets/6fdcf665-a627-430c-9c40-529654e214ba" />


# **Churn Prediction**

## **1\. Introduction**

Churn, also known as customer attrition, is one of the biggest challenges for telecommunications companies. It occurs when a customer decides to cancel their services, directly affecting the company’s revenue and business sustainability.Anticipating this behavior is essential for implementing preventive retention strategies, such as personalized offers and improved customer service.This project presents the development of a complete machine learning pipeline for churn prediction based on a real customer dataset, enabling the transformation of data into actionable insights.

## **2\. Problem Solved**

The analyzed telecom company faces difficulties in retaining customers and experiences a high churn rate. The main problem this project aims to solve is the early identification of customers with a higher probability of canceling their services. With this information, the company can take targeted actions, optimize resources, and reduce financial losses.

## **3\. Problem-Solving Approach**

The project was structured into four main complementary stages. In the data preparation phase, missing values were handled, irrelevant variables were removed, categorical variables were properly encoded, and numerical variables were standardized, resulting in consistent datasets for modeling. Next, in the feature selection phase, the Random Forest algorithm was used to calculate feature importance, keeping only the most relevant ones and reducing the problem’s dimensionality.

In the modeling phase, several algorithms were trained — Decision Tree, Logistic Regression, Random Forest, and LightGBM — and their performance was compared using metrics such as accuracy, precision, recall, F1-score, AUC, KS, and Gini. LightGBM stood out for its robustness and superior discriminative power. Finally, in the scoring phase, the best-performing model was applied to the entire customer base, generating individual churn probabilities that can be used in reports and retention strategies.

## **4\. Project Structure**

*  **01 \- Data Prep**: The raw dataset was processed to ensure quality and consistency. The target variable Churn was converted to binary format (0/1), missing values were imputed or removed, irrelevant variables were discarded, and categorical variables were encoded using Label Encoding and One-Hot Encoding. Numerical variables were standardized using StandardScaler, resulting in the final datasets abt\_train and abt\_test.


*  **02 \- Feature Selection**: With the data ready, feature selection was performed using the attribute importance scores from Random Forest. Only variables with importance greater than 10% of the maximum were retained. Correlation analysis was also performed to remove redundant features, resulting in a concise set containing only the most significant attributes.


*  **03 \- Modeling**: Four algorithms were trained and evaluated: Decision Tree, Logistic Regression, Random Forest, and LightGBM. Each model was compared using metrics such as AUC, KS, Gini, precision, recall, and F1-score. LightGBM was selected as the best-performing model, providing the best balance of predictive power, robustness, and generalization. The final model was saved for later use.


*  **04 \- Scoring**: The best model (LightGBM) was applied to 100% of the prepared dataset. Individual churn probabilities (score\_1) and final classifications (class) were generated for each customer. The results were exported to CSV files, ready to support retention strategies and decision-making by the company.

## **5\. Technologies Used**

*  **Language**: Python

*  **Main libraries**:

   *  pandas, numpy – data manipulation and analysis

   *  scikit-learn – preprocessing, modeling, and metrics

   *  lightgbm – efficient gradient boosting model

   *  matplotlib, seaborn – visualization and graphical analysis

## **6\. Results**

The LightGBM model was selected as the best-performing one, showing excellent performance in predicting churn. It achieved a high AUC, confirming its strong discriminative capacity, along with consistent KS and Gini metrics, indicating robustness and absence of overfitting. Another important outcome was the reduction of false positives, enabling more efficient targeting of retention actions and avoiding unnecessary costs for customers with no real risk of cancellation. The complete pipeline ensures reproducibility, as all artifacts were saved in .pkl files, and can be easily applied to new customer datasets to support the company’s strategic decision-making.

