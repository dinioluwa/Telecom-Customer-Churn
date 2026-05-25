#  Telecom Customer Churn Prediction

##  Project Overview
This project analyzes customer churn behavior for a telecom company 
using the Saiket systems Telco Customer Churn dataset. The goal is to identify 
key drivers of churn and build a predictive model that can flag 
at-risk customers before they leave thereby enabling proactive retention 
strategies.

---

##  Dataset
- **Source:** Saikets System — Telco Customer Churn
- **Size:** 7,043 customers × 21 features
- **Target Variable:** `Churn` (Yes / No)
- **Churn Rate:** ~26–32%

### Key Features
| Feature | Description |
|---------|-------------|
| `tenure` | Number of months the customer has been with the company |
| `MonthlyCharges` | Monthly amount charged to the customer |
| `TotalCharges` | Total amount charged over the customer's lifetime |
| `Contract` | Contract type (Month-to-month, One year, Two year) |
| `InternetService` | Type of internet service (DSL, Fiber optic, No) |
| `PaymentMethod` | Payment method used by the customer |
| `OnlineSecurity` | Whether the customer has online security add-on |
| `TechSupport` | Whether the customer has tech support add-on |
| `Churn` | Whether the customer churned (target variable) |

---

##  Tech Stack
- **Language:** Python 3
- **Libraries:**
  - `pandas` — data manipulation
  - `numpy` — numerical operations
  - `matplotlib` & `seaborn` — data visualization
  - `scikit-learn` — machine learning models and evaluation

---

##  Exploratory Data Analysis
Key insights uncovered during EDA:

- **Contract type** is the strongest predictor of churn
  - Month-to-month: ~41% churn rate
  - Two-year contract: ~3% churn rate
- **Early tenure customers** (0–12 months) churn the most (~45%)
- **Fiber optic customers** churn more despite paying higher charges
- Customers with **no add-on services** are significantly more likely to churn
- **Electronic check** users show the highest churn among payment methods

---

##  Models Trained

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Decision Tree | 76.7% | 53.8% | 48.3% | 50.9% |
| Random Forest | 79.0% | 59.0% | 46.0% | 52.0% |
| Tuned Random Forest | **80.0%** | **84.0%** | **90.0%** | **87.0%** |

### Best Model: Tuned Random Forest
- **AUC Score:** ~0.838
- **Best Parameters:** Found via GridSearchCV with 5-fold cross validation

---

## Top Features Driving Churn
1. `tenure` — shorter tenure = higher churn risk
2.  `TotalCharges` — reflects overall customer lifetime
3. `MonthlyCharges` — higher charges = more likely to leave
4. `InternetService_Fiber optic` — fiber customers churn more
5. `Contract_Two year` — long contracts = strong retention

---

##  Business Recommendations

| Priority | Action | Estimated Customers Saved |
|----------|--------|--------------------------|
| 🔴 High | Deploy churn model in CRM for real-time scoring | ~400/year |
| 🔴 High | Improve onboarding for first 90 days | ~350/year |
| 🟡 Medium | Launch contract upgrade campaign | ~300/year |
| 🟡 Medium | Bundle add-on services for at-risk customers | ~250/year |
| 🟢 Low | Incentivise auto-pay methods | ~150/year |

**Estimated Annual Revenue Impact: ~$1,346,400**

---

##  Results Summary
The Tuned Random Forest model achieves **80% accuracy** and an 
**AUC of ~0.84**, making it a reliable tool for identifying 
at-risk customers. Deploying this model in a production CRM system, 
combined with the recommended retention strategies, is estimated to 
save **~1,650 customers per year** and generate an additional 
**~$1.3M in annual revenue**.

---

##  Author
- **Name:** deborah adeyemo
- **Email:** dinioluwa196@gmail.com
- **LinkedIn:** www.linkedin.com/in/adeyemodeborahaa2016
- **GitHub:** github.com/dinioluwa
