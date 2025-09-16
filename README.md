📞 KTL Customer Churn Prediction Project

Author: Jeff Kandie
LinkedIn: https://www.linkedin.com/in/jeff-kandie/

Project Overview

This project focuses on predicting customer churn for KTL Telecommunications, a critical problem in the telecom industry where high competition and low switching barriers make retaining customers essential. Accurately identifying customers likely to churn allows the company to proactively implement retention strategies, reduce costs, and improve service quality.

Business Understanding

Problem: KTL faces significant revenue loss due to customer churn. Without predictive insights, marketing efforts are inefficient and resources are wasted on loyal customers.

Impact: High churn directly affects profitability and signals potential service issues.

Objective: Build a predictive model to identify high-risk churn customers and provide actionable insights for retention.

Key Metrics:

Accuracy > 75%

Recall > 70% (to ensure high detection of churners)

Data Understanding

The dataset contains 21 columns representing customer demographics, account details, service usage, and subscription plans. Key features include:

account length: Customer tenure

international plan & voice mail plan: Subscription plans

total day/eve/night/intl minutes & calls: Call usage patterns

customer service calls: Number of support interactions

churn: Target variable (1 if customer churned, 0 otherwise)

Observations from Exploratory Data Analysis (EDA):

Customers with high service calls are more likely to churn.

International plan users have a higher churn rate (~42%) compared to non-users.

Voicemail plan subscribers show lower churn (~8.7%).

Heavy daytime users pay higher charges and are more likely to leave.

Data Preparation & Feature Engineering

Cleaning: Removed phone numbers and duplicate records, handled missing values.

Encoding: Converted categorical variables (plans, bins) into numeric representations.

Feature Engineering:

call_intensity – average call duration

service_frustration – flag for customers with ≥4 service calls

plan_combo – interaction between international and voicemail plan

day_usage_bin – binned daytime usage

Scaling & Preprocessing: StandardScaler applied to numerical features; One-Hot Encoding for categorical variables.

Class Balancing: Used SMOTE to handle class imbalance.

Modeling

Tested multiple models including:

Model	Accuracy	Recall
Logistic Regression	~91%	~65%
Decision Tree	~92%	~68%
Random Forest	~93%	~74%
XGBoost	~94%	~76%

Top features influencing churn:

international plan

customer service calls

total day minutes

total day charge

call_intensity

Best-performing models for deployment: Random Forest and XGBoost (after SMOTE balancing).

Key Insights

Customers contacting support frequently and with high daytime usage are more likely to churn.

International plan users have significantly higher churn risk.

Voicemail plan reduces churn, acting as a loyalty feature.

Heavy users experiencing high charges with unresolved issues are prime targets for retention campaigns.

Recommendations

Retention Programs: Target high-risk churn customers (high day usage, multiple service calls, international plan users) with personalized offers.

Service Improvements: Enhance customer support efficiency to reduce frustration.

Plan Optimization: Review international plan pricing and features for better value.

Engagement Initiatives: Promote voicemail and other value-added services to increase loyalty.

Continuous Monitoring: Implement real-time churn prediction dashboards for proactive interventions.

Tools & Libraries

Python: pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost

Imbalanced-learn: SMOTE for class balancing

Statistical analysis: scipy.stats

Conclusion

The project successfully built a predictive churn model for KTL with high recall, allowing early identification of at-risk customers. By combining insights from feature importance and statistical analysis, KTL can target retention strategies effectively, reduce customer loss, and improve overall profitability
