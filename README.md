# 📡 Telco Customer Churn Analysis using Python & Power BI

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

*Uncovering the hidden patterns behind customer churn to drive smarter retention strategies.*

</div>

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Problem Statement](#-business-problem-statement)
- [Objectives](#-objectives)
- [Dataset Description](#-dataset-description)
- [Technologies Used](#-technologies-used)
- [Project Workflow](#-project-workflow)
- [Key Insights](#-key-insights)
- [Power BI Dashboard](#-power-bi-dashboard)
- [Business Recommendations](#-business-recommendations)
- [Future Scope](#-future-scope)
- [Folder Structure](#-folder-structure)
- [How to Run](#-how-to-run)
- [Conclusion](#-conclusion)

---

## 🧩 Project Overview

Customer churn is one of the most critical challenges in the telecom industry. Losing a customer is significantly more expensive than acquiring one — making early identification of at-risk customers a top business priority.

This end-to-end data analytics project analyzes a telecom company's customer data to **identify churn patterns, uncover root causes, and deliver actionable retention strategies**. The project combines the power of **Python for data analysis and visualization** with **Power BI for interactive business dashboards** — a complete analytics stack used by modern data professionals.

---

## 💼 Business Problem Statement

> *A telecom company is experiencing a high rate of customer churn, resulting in significant revenue loss. The business needs to understand **why customers are leaving**, **who is most likely to churn**, and **what actions can be taken** to improve customer retention and lifetime value.*

Without data-driven insights, retention efforts are scattered and inefficient. This project provides the analytical foundation to make those efforts targeted and effective.

---

## 🎯 Objectives

- ✅ Clean and preprocess raw telecom customer data for analysis
- ✅ Perform comprehensive Exploratory Data Analysis (EDA)
- ✅ Identify key variables strongly correlated with customer churn
- ✅ Segment customers by risk level and behavioral patterns
- ✅ Visualize findings using Python (Matplotlib & Seaborn)
- ✅ Build an interactive Power BI dashboard for business stakeholders
- ✅ Translate analytical findings into actionable business recommendations

---

## 📊 Dataset Description

The dataset contains **7,043 telecom customer records** with the following features:

| Feature | Type | Description |
|---|---|---|
| `CustomerID` | Categorical | Unique customer identifier |
| `Gender` | Categorical | Male / Female |
| `SeniorCitizen` | Binary | Whether the customer is a senior citizen (1/0) |
| `Partner` | Categorical | Whether the customer has a partner |
| `Dependents` | Categorical | Whether the customer has dependents |
| `Tenure` | Numerical | Number of months with the company |
| `PhoneService` | Categorical | Phone service subscription |
| `InternetService` | Categorical | DSL / Fiber Optic / None |
| `Contract` | Categorical | Month-to-Month / One Year / Two Year |
| `PaymentMethod` | Categorical | Electronic Check, Mailed Check, etc. |
| `MonthlyCharges` | Numerical | Monthly billing amount (USD) |
| `TotalCharges` | Numerical | Total amount billed (USD) |
| `Churn` | Binary (Target) | Whether the customer churned (Yes/No) |

> 📁 **Source:** [IBM Sample Dataset / Kaggle Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

---

## 🛠️ Technologies Used

| Tool / Library | Purpose |
|---|---|
| 🐍 **Python 3.10+** | Core programming language |
| 🐼 **Pandas** | Data manipulation and preprocessing |
| 🔢 **NumPy** | Numerical computations |
| 📊 **Matplotlib** | Static data visualization |
| 🎨 **Seaborn** | Statistical and aesthetic visualizations |
| 📈 **Power BI Desktop** | Interactive business dashboard |
| 📓 **Jupyter Notebook** | Development and presentation environment |

---

## 🔄 Project Workflow

```
Raw Data (.csv)
      │
      ▼
┌─────────────────────┐
│  1. Data Loading &  │
│     Inspection      │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  2. Data Cleaning & │
│    Preprocessing    │  ← Handle nulls, fix dtypes, encode categoricals
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  3. Exploratory     │
│  Data Analysis (EDA)│  ← Distributions, correlations, churn rates by segment
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  4. Python          │
│  Visualizations     │  ← Bar charts, pie charts, heatmaps, box plots
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  5. Power BI        │
│  Dashboard          │  ← Interactive filters, KPIs, drill-throughs
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  6. Insights &      │
│  Recommendations    │  ← Business-ready findings
└─────────────────────┘
```

---

## 💡 Key Insights

### 1. 📋 Contract Type is the Strongest Churn Predictor
Month-to-month contract customers exhibited the **highest churn rate (~42%)**, compared to one-year (~11%) and two-year (~3%) contract holders. Longer commitments strongly correlate with retention.

### 2. ⏳ Tenure Matters — New Customers Are at Highest Risk
Customers with **tenure under 12 months** showed significantly higher churn rates. The first year is the most critical window for retention efforts.

### 3. 💳 Payment Method Influences Churn Behavior
Customers paying via **electronic check had the highest churn rate** compared to automatic payment methods (credit card, bank transfer). Friction in payment may signal lower engagement.

### 4. 🌐 Internet Service Type Correlates with Churn
**Fiber optic users had a relatively higher churn rate** than DSL users, suggesting potential issues with pricing perception or service quality expectations.

### 5. 👴 Senior Citizens Are a High-Risk Segment
Senior citizens (SeniorCitizen = 1) showed a notably **higher propensity to churn**, potentially due to service complexity, cost sensitivity, or inadequate support.

### 6. 💰 Higher Monthly Charges = Higher Churn Risk
Churned customers had **higher average monthly charges** compared to retained customers, indicating that pricing and perceived value are key friction points.

---

## 📊 Power BI Dashboard

The interactive Power BI dashboard provides stakeholders with a real-time view of churn metrics, customer segmentation, and KPIs.

### Dashboard Preview

> **Page 1 — Churn Overview**

![Dashboard Overview](assets/screenshots/dashboard_overview.png)
*← Replace with your actual screenshot*

> **Page 2 — Customer Segmentation**

![Customer Segmentation](assets/screenshots/dashboard_segmentation.png)
*← Replace with your actual screenshot*

> **Page 3 — Revenue Impact Analysis**

![Revenue Impact](assets/screenshots/dashboard_revenue.png)
*← Replace with your actual screenshot*

### Dashboard Features
- 🔢 **KPI Cards** — Total Customers, Churn Rate %, Avg Tenure, Avg Monthly Charges
- 🎛️ **Interactive Slicers** — Filter by Contract Type, Gender, Internet Service, Senior Citizen
- 📊 **Churn by Segment Charts** — Contract, Payment Method, Tenure Band, Internet Service
- 📉 **Trend Analysis** — Monthly charges distribution for churned vs retained customers
- 🗺️ **Customer Risk Matrix** — Segment-level churn risk visualization

> 📂 Dashboard file: `powerbi/Telco_Churn_Dashboard.pbix`

---

## 📌 Business Recommendations

Based on the analytical findings, the following strategies are recommended:

| Priority | Recommendation | Target Segment |
|---|---|---|
| 🔴 High | **Improve new customer onboarding** — proactive check-ins in months 1–6 | Tenure < 6 months |
| 🔴 High | **Promote annual & two-year contracts** with discounts/incentives | Month-to-Month customers |
| 🟠 Medium | **Incentivize auto-payment enrollment** to reduce electronic check usage | Electronic check users |
| 🟠 Medium | **Dedicated retention campaigns** for fiber optic subscribers | Fiber Optic users |
| 🟡 Medium | **Senior citizen support program** — simplified plans, dedicated helpline | SeniorCitizen = 1 |
| 🟡 Low | **Loyalty rewards program** for customers approaching 12-month milestone | Tenure 9–12 months |
| 🟢 Low | **Price sensitivity analysis** to evaluate plan restructuring | High monthly charge tier |

---

## 🚀 Future Scope

This project establishes a strong analytical foundation. Future enhancements can significantly amplify its business impact:

- **🤖 Predictive Churn Modeling** — Implement ML classifiers (Logistic Regression, Random Forest, XGBoost) to predict individual customer churn probability with a risk score
- **⚙️ Real-Time Churn Scoring Pipeline** — Deploy the model as a REST API (FastAPI/Flask) to score new customers in real time and trigger automated retention workflows
- **🧠 Customer Lifetime Value (CLV) Integration** — Combine churn probability with CLV to prioritize retention efforts on the most valuable at-risk customers
- **📬 Personalized Retention Triggers** — Build automated alert systems using Power Automate or Python to notify CRM teams when a customer's churn risk exceeds a threshold
- **🌐 NLP on Support Tickets** — Analyze customer support call logs and reviews using NLP/sentiment analysis to surface hidden churn drivers
- **📅 Cohort & Survival Analysis** — Apply Kaplan-Meier survival curves to model churn over the customer lifecycle more precisely
- **📊 Advanced Power BI Features** — Integrate AI visuals (Key Influencers, Decomposition Tree) and publish to Power BI Service for organization-wide sharing

---

## 📁 Folder Structure

```
telco-customer-churn-analysis/
│
├── 📂 data/
│   ├── raw/
│   │   └── telco_customer_churn.csv          # Original dataset
│   └── processed/
│       └── telco_cleaned.csv                 # Cleaned dataset
│
├── 📂 notebooks/
│   ├── 01_data_cleaning.ipynb                # Data preprocessing steps
│   ├── 02_eda.ipynb                          # Exploratory Data Analysis
│   └── 03_visualizations.ipynb               # Python charts & plots
│
├── 📂 powerbi/
│   └── Telco_Churn_Dashboard.pbix            # Power BI dashboard file
│
├── 📂 assets/
│   └── screenshots/
│       ├── dashboard_overview.png
│       ├── dashboard_segmentation.png
│       └── dashboard_revenue.png
│
├── 📂 reports/
│   └── churn_analysis_report.pdf            # Summary report (optional)
│
├── 📄 requirements.txt                       # Python dependencies
├── 📄 README.md                              # Project documentation
└── 📄 LICENSE
```

---

## ▶️ How to Run

### Prerequisites
- Python 3.8 or higher
- Power BI Desktop (free download from Microsoft)
- Jupyter Notebook or JupyterLab

### Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/telco-customer-churn-analysis.git
cd telco-customer-churn-analysis
```

### Step 2 — Set Up Python Environment

```bash
# Create and activate a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# Install required libraries
pip install -r requirements.txt
```

### Step 3 — Run the Notebooks

```bash
jupyter notebook
```

Open and run the notebooks in order:
1. `notebooks/01_data_cleaning.ipynb`
2. `notebooks/02_eda.ipynb`
3. `notebooks/03_visualizations.ipynb`

### Step 4 — Open Power BI Dashboard

1. Launch **Power BI Desktop**
2. Open `powerbi/Telco_Churn_Dashboard.pbix`
3. Refresh the data source if prompted (point to `data/processed/telco_cleaned.csv`)
4. Explore the interactive dashboard

### Requirements (`requirements.txt`)

```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
openpyxl>=3.0.0
```

---

## ✅ Conclusion

This project delivers a comprehensive, end-to-end analysis of customer churn in the telecom industry. By combining **Python-driven EDA** with an **interactive Power BI dashboard**, the analysis translates raw data into clear, actionable business intelligence.

The findings clearly show that **contract type, customer tenure, and payment method** are the primary levers for churn reduction. Businesses that act on these insights — through proactive onboarding, contract migration incentives, and targeted retention programs — can expect a measurable improvement in customer lifetime value and revenue stability.

This project demonstrates a complete data analytics workflow applicable across industries, from financial services to SaaS and retail.

---

<div align="center">

**⭐ If you found this project useful, please give it a star!**

Made with ❤️ using Python & Power BI

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username)

</div>
