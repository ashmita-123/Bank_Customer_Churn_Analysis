<div align="center">

# Bank Customer Churn Analysis

**End-to-end churn analytics project using Python (data cleaning, validation, feature engineering, EDA) and Power BI (interactive dashboard).**

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

</div>

---

## Overview

Customer churn — when a customer stops doing business with a bank — is one of the costliest problems in retail banking, since retaining an existing customer is far cheaper than acquiring a new one. This project analyzes a dataset of **10,000 bank customers** to understand **who churns, why they churn, and where the bank should focus retention efforts.**

The project is split into two parts:

1. **Python (Jupyter Notebook)** — data loading, inspection, cleaning, validation, feature engineering, and exploratory data analysis (EDA).
2. **Power BI** — a 4-page interactive dashboard built on the cleaned dataset, designed for both executives and front-line staff.

A full write-up of the project (methodology, code, charts, dashboard walkthrough, and business insights) is available in [`Bank_Customer_Churn_Analysis_Report.pdf`](./Bank_Customer_Churn_Analysis_Report.pdf).

---

## Objectives

- Clean and validate a raw, 21-column bank customer dataset.
- Engineer new features (age groups, credit score bands, income categories, activity levels, etc.) for richer segmentation.
- Explore how churn varies across demographic, financial, account, and behavioral attributes.
- Identify the strongest churn drivers using correlation analysis.
- Build an interactive Power BI dashboard for churn monitoring and customer-level lookup.
- Translate findings into clear, actionable business recommendations.

---

## Dataset

- **Rows:** 10,000 customers
- **Original columns:** 21 (demographic, account, credit, loan, and behavioral attributes)
- **Engineered columns:** 7 additional features created during analysis
- **Target variable:** `Churn` (1 = churned, 0 = stayed)

<details>
<summary><strong>Click to expand full column list</strong></summary>

| # | Column | Description |
|---|--------|-------------|
| 1 | `Customer_ID` | Unique customer identifier |
| 2 | `Full_Name` | Customer's full name |
| 3 | `Age` | Customer age (18–75) |
| 4 | `Gender` | Male / Female |
| 5 | `State` | Indian state of residence (20 states) |
| 6 | `City` | City of residence (90 cities) |
| 7 | `Account_Type` | Savings / Premium / Current / Salary |
| 8 | `Tenure_Years` | Years as a bank customer (1–15) |
| 9 | `Account_Balance` | Current account balance (INR) |
| 10 | `Num_Products` | Number of banking products held (1–4) |
| 11 | `Has_Credit_Card` | Yes / No |
| 12 | `Loan_Status` | Active / Closed / No Loan |
| 13 | `Credit_Score` | Credit score (420–850) |
| 14 | `Monthly_Income` | Monthly income (INR) |
| 15 | `Loan_Amount` | Outstanding loan amount (INR) |
| 16 | `Transactions_Per_Month` | Avg. transactions per month (7–49) |
| 17 | `Last_Transaction_Date` | Date of last transaction |
| 18 | `Mobile_Banking` | Yes / No |
| 19 | `UPI_Usage` | Yes / No |
| 20 | `Complaints` | Number of complaints filed (0–6) |
| 21 | `Churn` | Target — 1 = churned, 0 = stayed |

**Engineered features:** `Churn_Status`, `Age_Group`, `Credit_Score_Group`, `Balance_Category`, `Income_Category`, `Days_Since_Last_Transaction`, `Activity_Category`

</details>

---

## Tools & Technologies

| Category | Tools |
|---|---|
| Language | Python 3 |
| Libraries | Pandas, NumPy, Matplotlib, Seaborn |
| Environment | Jupyter Notebook |
| Dashboard | Microsoft Power BI Desktop |
| Interchange format | CSV |

---

## Project Workflow

```
Raw CSV (21 cols)
      │
      ▼
Data Inspection  →  shape, dtypes, nulls, duplicates, unique values
      │
      ▼
Data Cleaning    →  whitespace trimming, text case standardization, date parsing
      │
      ▼
Data Validation  →  range checks + logical consistency checks
      │
      ▼
Feature Engineering → 7 new columns (Age_Group, Credit_Score_Group, etc.)
      │
      ▼
Exploratory Data Analysis → churn rate by every attribute + correlation matrix
      │
      ▼
Cleaned CSV (28 cols)
      │
      ▼
Power BI Dashboard → Overview | Churn Drivers | Segmentation | Customer Details
```

---

## 📊 Key Findings

| Driver | Effect | Finding |
|---|---|---|
| 🔴 **Complaints** | Strongest driver | Churn jumps from **16.3%** (0 complaints) to **56.1%** (4 complaints) |
| 🟢 **Number of Products** | Protective | Churn drops from **20.4%** (1 product) to **14.9%** (3 products) |
| 🟢 **Mobile Banking / UPI** | Protective | Non-users churn at **23.2% / 20.9%** vs **17.0% / 17.3%** for users |
| 🟠 **Tenure (Year 1)** | Early-tenure risk | First-year customers churn the most, at **21.3%** |
| 🟠 **Premium Accounts** | Elevated risk | Highest churn among account types, at **19.2%** |
| 🟠 **Geography** | Regional variation | Haryana (23.7%) and Gurugram (26.6%) are the highest-churn state/city |

**Overall churn rate: 18.38%** (1,838 of 10,000 customers)

> No single variable strongly predicts churn on its own (all correlations with `Churn` fall between −0.05 and +0.08) — retention strategy needs to combine service quality, product depth, and digital engagement signals rather than relying on one metric.

---

## 📈 Power BI Dashboard

The dashboard has **4 pages**:

| Page | Purpose |
|---|---|
| **Overview** | Executive KPIs + churn by gender, age group, account type, top-10 states |
| **Churn Drivers** | Churn by credit score group, number of products, activity category, mobile banking |
| **Customer Segmentation** | Customer distribution + churn by income, balance, and loan status |
| **Customer Details** | Searchable, single-customer drill-down profile |

<!--
Add your dashboard screenshots here, e.g.:
![Overview Page](assets/dashboard_overview.png)
![Churn Drivers Page](assets/dashboard_churn_drivers.png)
![Customer Segmentation Page](assets/dashboard_segmentation.png)
![Customer Details Page](assets/dashboard_customer_details.png)
-->

## Future Improvements

- Train a predictive model (Logistic Regression / Random Forest / XGBoost) to score churn probability per customer
- Add Customer Lifetime Value (CLV) estimation
- Incorporate transaction-level time-series data for trend/cohort analysis
- Automate the Power BI data refresh pipeline
- Deploy a churn-risk score directly into the Customer Details dashboard page

---

## Author

**Ashmita**
BCA (Bachelor of Computer Applications) Student

---

## License

This project is open-sourced for learning and portfolio purposes. Feel free to fork, explore, and build on it.
