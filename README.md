# Telco Customer Churn Analysis using AFT Models

This project applies survival analysis techniques to predict customer churn and estimate Customer Lifetime Value (CLV) using the Accelerated Failure Time (AFT) models.

## 📂 Dataset

The dataset contains telecom subscriber information, including demographic, socioeconomic, and service usage data. Key columns:
- `tenure`: customer lifetime (target)
- `churn`: whether the customer churned (event indicator)
- `custcat`, `region`, `income`, `internet`, `voice`, etc.

## 📈 Objective

- Build and compare AFT survival models (Weibull, Log-Logistic, Log-Normal)
- Identify significant predictors of churn
- Visualize survival curves
- Calculate CLV per customer
- Segment customers and analyze retention value

## ✅ Final Model

The **LogNormal AFT** model was selected based on the lowest AIC. Key predictors include:
- **Age**, **Customer Category**, **Internet Usage**, **Voice Plan**, **Marital Status**

## 💰 CLV Calculation

CLV is calculated for each customer using predicted median survival time, an assumed ARPU (Average Revenue Per User), and a monthly discount rate.

Formula used:
CLV = (ARPU × [1 - (1 + r)^-t]) / r

## Where:
- `r` = discount rate
- `t` = predicted median lifetime

## 🔍 Insights

- High-value segments: older, married, and total-service customers
- At-risk: younger, unmarried users with internet/voice services
- Recommended retention budget: based on CLV and survival analysis

## 📦 Files Included

- `telco.csv` — dataset
- `AFT_Modeling.ipynb` — full modeling and CLV code
- `requirements.txt` — dependencies
- `report.md` — summary insights

## ⚙️ Requirements

Install required Python libraries:

```bash
pip install -r requirements.txt
