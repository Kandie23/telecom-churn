# 📞 KTL Customer Churn Prediction Project

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

**Author:** Jeff Kandie  
**LinkedIn:** [https://www.linkedin.com/in/jeffkandie](https://www.linkedin.com/in/jeffkandie)  

---

## Table of Contents
- [Project Overview](#project-overview)
- [Business Understanding](#business-understanding)
- [Data Understanding](#data-understanding)
- [Data Preparation & Feature Engineering](#data-preparation--feature-engineering)
- [Modeling](#modeling)
- [Key Insights](#key-insights)
- [Recommendations](#recommendations)
- [Tools & Libraries](#tools--libraries)
- [Conclusion](#conclusion)
- [License](#license)

---

## Project Overview
This project focuses on predicting **customer churn** for KTL Telecommunications, a critical issue in the highly competitive telecom industry. Accurately identifying customers likely to churn allows the company to:  
- Proactively implement retention strategies  
- Reduce customer acquisition costs  
- Improve service quality and profitability  

---

## Business Understanding
- **Problem:** KTL experiences significant revenue loss due to customer churn. Without predictive insights, marketing and retention efforts are inefficient.  
- **Impact:** High churn directly affects profitability and signals potential service issues.  
- **Objective:** Build a predictive model to identify high-risk churn customers and provide actionable insights.

**Key Metrics:**
- Accuracy > 75%
- Recall > 70% (to detect churners effectively)

---

## Data Understanding
The dataset contains **21 columns** describing customer demographics, account details, service usage, and subscription plans.  

**Key Features:**
| Feature | Description |
|---------|-------------|
| account length | Customer tenure |
| international plan | Subscription status (Yes/No) |
| voice mail plan | Subscription status (Yes/No) |
| total day/eve/night/intl minutes & calls | Call usage patterns |
| customer service calls | Number of support interactions |
| churn | Target variable (1 = churned, 0 = retained) |

**EDA Observations:**
- High **customer service calls** → higher churn probability  
- **International plan users** → 42% churn rate  
- **Voicemail plan subscribers** → lower churn (~8.7%)  
- Heavy daytime usage → higher dissatisfaction and churn risk  

---

## Data Preparation & Feature Engineering
1. **Cleaning:** Removed duplicates, phone numbers, and handled missing values.  
2. **Encoding:** Categorical variables encoded to numeric values.  
3. **Feature Engineering:**  
   - `call_intensity` – average call duration  
   - `service_frustration` – flag for ≥4 service calls  
   - `plan_combo` – interaction of international and voicemail plan  
   - `day_usage_bin` – binned daytime usage  
4. **Scaling:** StandardScaler for numeric features  
5. **Class Balancing:** SMOTE applied to handle imbalanced target variable  

---

## Modeling
Models tested: Logistic Regression, Decision Tree, Random Forest, XGBoost  

| Model                 | Accuracy | Recall |
|-----------------------|----------|--------|
| Logistic Regression    | ~91%    | ~65%   |
| Decision Tree          | ~92%    | ~68%   |
| Random Forest          | ~93%    | ~74%   |
| XGBoost                | ~94%    | ~76%   |

**Top features influencing churn:**  
1. `international plan`  
2. `customer service calls`  
3. `total day minutes`  
4. `total day charge`  
5. `call_intensity`  

**Best-performing models for deployment:** Random Forest & XGBoost (after SMOTE balancing)  

---

## Key Insights
- **Frequent support calls** = major churn signal  
- **High daytime usage** = higher dissatisfaction  
- **International plan** = strong churn driver  
- **Voicemail plan** = reduces churn, increases engagement  
- **Heavy users with service issues** = highest churn risk  

---

## Recommendations
1. **Retention Programs:** Target high-risk churn customers with personalized offers.  
2. **Service Improvements:** Improve customer support efficiency.  
3. **Plan Optimization:** Reevaluate international plan pricing and value.  
4. **Engagement Initiatives:** Promote value-added services like voicemail.  
5. **Monitoring:** Implement real-time churn prediction dashboards.  

---

## Tools & Libraries
- Python: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`  
- Imbalanced-learn: `SMOTE` for class balancing  
- Statistical analysis: `scipy.stats`  

---

## Conclusion
The project successfully built a **predictive churn model** for KTL with high recall. The insights allow KTL to:  
- Identify high-risk churn customers early  
- Optimize retention strategies  
- Reduce revenue loss and improve customer satisfaction  

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
