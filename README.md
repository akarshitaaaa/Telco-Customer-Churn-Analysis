# 📡 Telco Customer Churn Analysis — Python & Power BI

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

*An end-to-end customer churn analysis project — from raw data cleaning to a single-page interactive Power BI dashboard — built to uncover why customers leave and what keeps them.*

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Problem Statement](#-business-problem-statement)
- [Objectives](#-objectives)
- [Dataset Description](#-dataset-description)
- [Technologies Used](#️-technologies-used)
- [Project Workflow](#-project-workflow)
- [Key Insights](#-key-insights)
- [Power BI Dashboard](#-power-bi-dashboard)
- [Business Recommendations](#-business-recommendations)
- [Limitations](#-limitations)
- [Future Scope](#-future-scope)
- [Folder Structure](#-folder-structure)
- [How to Run](#️-how-to-run)
- [Conclusion](#-conclusion)

---

## 🧩 Project Overview

Customer churn is one of the most expensive problems in the telecom industry — retaining an existing customer is generally far cheaper than acquiring a new one. This project performs a **descriptive analytics pipeline** on a real telecom dataset to identify *who* is churning and *what patterns* are associated with it, so the business can design targeted retention strategies.

The project combines **Python (Pandas, NumPy, Matplotlib, Seaborn)** for data cleaning and exploratory data analysis with a **single-page Power BI Customer Dashboard** that compares the overall customer base against churned customers side by side.

> This is a descriptive analytics project, not a predictive one — the goal is to explain patterns behind past churn, not to forecast future churn with a model.

---

## 💼 Business Problem Statement

> A telecom company has a churn rate of **26.54%** — more than 1 in 4 customers are leaving. The business needs to understand which customer segments churn the most and why, so it can prioritize retention efforts where they matter most.

---

## 🎯 Objectives

- ✅ Clean and preprocess the raw dataset (fix data types, validate nulls and duplicates, encode features for readability)
- ✅ Perform Exploratory Data Analysis (EDA) across all 21 features
- ✅ Identify customer segments with the highest churn rates
- ✅ Visualize churn patterns using Python (Matplotlib & Seaborn)
- ✅ Build an interactive **single-page Customer Dashboard** in Power BI comparing all customers vs. churned customers
- ✅ Translate findings into concrete, prioritized business recommendations

---

## 📊 Dataset Description

**File:** `Telco-Customer-Churn.csv` **Records:** 7,043 customers | **Features:** 21 columns | **Target:** `Churn` (Yes / No) **Source:** IBM Telco Customer Churn dataset (Kaggle)

| #  | Column             | Type            | Description                                                      |
| -- | ------------------ | --------------- | ------------------------------------------------------------------ |
| 1  | `customerID`       | Categorical     | Unique customer identifier                                        |
| 2  | `gender`           | Categorical     | Male / Female                                                     |
| 3  | `SeniorCitizen`    | Binary          | 1 = Senior, 0 = Non-Senior (mapped to Yes/No in analysis)         |
| 4  | `Partner`          | Categorical     | Whether the customer has a partner                                |
| 5  | `Dependents`       | Categorical     | Whether the customer has dependents                                |
| 6  | `tenure`           | Numerical       | Months the customer has been with the company                     |
| 7  | `PhoneService`     | Categorical     | Phone service subscription                                         |
| 8  | `MultipleLines`    | Categorical     | Multiple phone lines                                               |
| 9  | `InternetService`  | Categorical     | DSL / Fiber optic / No                                              |
| 10 | `OnlineSecurity`   | Categorical     | Online security add-on                                             |
| 11 | `OnlineBackup`     | Categorical     | Online backup add-on                                               |
| 12 | `DeviceProtection` | Categorical     | Device protection add-on                                          |
| 13 | `TechSupport`      | Categorical     | Tech support add-on                                                |
| 14 | `StreamingTV`      | Categorical     | TV streaming subscription                                          |
| 15 | `StreamingMovies`  | Categorical     | Movie streaming subscription                                       |
| 16 | `Contract`         | Categorical     | Month-to-month / One year / Two year                               |
| 17 | `PaperlessBilling` | Categorical     | Paperless billing enabled                                          |
| 18 | `PaymentMethod`    | Categorical     | Electronic check / Mailed check / Bank transfer / Credit card      |
| 19 | `MonthlyCharges`   | Numerical       | Monthly billing amount (USD)                                       |
| 20 | `TotalCharges`     | Numerical       | Total amount billed (originally stored as text — fixed in cleaning)|
| 21 | `Churn`            | Binary (Target) | Whether the customer churned: **Yes (1,869) / No (5,174)**         |

> **Data Quality Note:** `TotalCharges` contained 11 blank-space entries (new customers with `tenure = 0`, not yet billed) — replaced with `"0"` and cast to `float`. `SeniorCitizen` (0/1) was mapped to `Yes/No` for readability. No duplicate `customerID` values or nulls were found after cleaning.

---

## 🛠️ Technologies Used

| Tool / Library         | Purpose                                             |
| ----------------------- | ---------------------------------------------------- |
| 🐍 **Python**            | Core language for data cleaning and EDA              |
| 🐼 **Pandas**            | Data loading, cleaning, transformation               |
| 🔢 **NumPy**             | Numerical operations                                  |
| 📊 **Matplotlib**        | Base plotting                                         |
| 🎨 **Seaborn**           | Statistical visualizations (countplots, histplots)    |
| 📈 **Power BI Desktop**  | Single-page interactive dashboard with KPI cards & slicer |
| 📓 **Jupyter Notebook**  | Development and analysis workspace                     |

---

## 🔄 Project Workflow

```
Telco-Customer-Churn.csv
          │
          ▼
┌──────────────────────────┐
│   STEP 1: Data Loading   │  df = pd.read_csv(...)
│   & Initial Inspection   │  df.head() / df.shape / df.info()
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│  STEP 2: Data Cleaning   │  Fix TotalCharges dtype (text → float)
│  & Preprocessing         │  Map SeniorCitizen 0/1 → Yes/No
│                          │  Check nulls, check duplicate customerIDs
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│   STEP 3: EDA &          │  Churn distribution (count + pie chart)
│   Visualizations         │  Churn by: Gender, SeniorCitizen, Tenure,
│   (Python)               │  Contract, PaymentMethod, InternetService,
│                          │  and a 3x3 grid of service-type columns
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│   STEP 4: Power BI       │  Single-page Customer Dashboard
│   Dashboard              │  All Customers vs. Churned Customers panels
│   Customer_Dashboard     │  KPI cards, pie charts, bar charts,
│   .pbix                  │  tenure line chart, Senior Citizen slicer
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│   STEP 5: Insights &     │  Segment-level churn rates quantified
│   Recommendations        │  Business actions prioritized
└──────────────────────────┘
```

---

## 💡 Key Insights

All figures below are computed directly from `Telco-Customer-Churn.csv`.

### 1. 📋 Contract Type is the #1 Churn Driver

| Contract       | Churn Rate |
| -------------- | ---------- |
| Month-to-month | **42.7%**  |
| One year       | 11.3%      |
| Two year       | **2.8%**   |

Month-to-month customers churn at over **15× the rate** of two-year contract holders — and month-to-month contracts alone account for **89% of all churned customers**, despite being only 55% of the total base.

### 2. ⏳ New Customers Churn Far More Than Long-Tenured Ones

Average tenure of churned customers is **18.0 months**, versus **37.6 months** for retained customers. Churn is heavily concentrated in the first year — the earliest months of the customer relationship are the highest-risk window.

### 3. 💳 Electronic Check Users Have the Highest Churn Rate

| Payment Method             | Churn Rate |
| --------------------------- | ---------- |
| Electronic check            | **45.3%**  |
| Mailed check                | 19.1%      |
| Bank transfer (automatic)   | 16.7%      |
| Credit card (automatic)     | **15.2%**  |

Electronic check users churn at roughly **3× the rate** of automatic-payment users — worth investigating further (payment friction, failed transactions, or simply a less-engaged customer segment).

### 4. 🌐 Fiber Optic Users Churn at More Than Double the Rate of DSL

| Internet Service     | Churn Rate |
| ---------------------- | ---------- |
| Fiber optic            | **41.9%**  |
| DSL                    | 19.0%      |
| No internet service    | 7.4%       |

Fiber optic is a premium product, yet has the highest churn — this is a correlation worth investigating (pricing, service quality, or support experience), not an established cause.

### 5. 👴 Senior Citizens Churn at Nearly Double the Rate

| Segment            | Churn Rate |
| -------------------- | ---------- |
| Non-Senior           | 23.6%      |
| Senior Citizen       | **41.7%**  |

Senior citizens make up only ~16% of the customer base but represent a disproportionately high-risk segment.

### 6. 💰 Churned Customers Pay More on Average

| Churn Status  | Avg Monthly Charges |
| --------------- | -------------------- |
| Retained (No)   | $61.27                |
| Churned (Yes)   | **$74.44**            |

Churned customers pay about **$13/month more** on average — pointing to possible price sensitivity or a perceived value gap.

### 7. ⚧ Gender Has Minimal Impact on Churn

| Gender | Churn Rate |
| ------- | ---------- |
| Female  | 26.9%      |
| Male    | 26.2%      |

Churn is nearly identical across genders — gender is **not** a meaningful variable for targeting retention campaigns.

---

## 📊 Power BI Dashboard

The **Customer Dashboard** (`Customer_Dashboard.pbix`) is a **single-page** interactive report — there is no separate Q&A page or additional tabs. The one dashboard page is split into two mirrored panels for direct comparison:

| Panel                  | Purpose                                                       |
| ------------------------ | -------------------------------------------------------------- |
| **All Customers**       | Baseline profile across the full 7,043-customer base            |
| **Churned Customers**    | Same breakdown, filtered to the 1,869 customers who churned     |

### Visuals on the Dashboard

- 🃏 **KPI Cards** — Total Customers (7,043), Churned Customers (1,869), Senior Citizens (1,142 total / 476 churned)
- 📈 **Line Chart** — Tenure distribution (all vs. churned)
- 📊 **Bar Chart** — Payment Method breakdown
- 🥧 **Pie Chart** — Contract Type split
- 🥧 **Pie Chart** — Internet Service split
- 📊 **Bar Chart** — Partner status (Yes/No)
- 📊 **Bar Chart** — Gender breakdown
- 🎛️ **Slicer** — Filter the entire dashboard by Senior Citizen status (All / Yes / No)

### Dashboard Preview

**Main Dashboard Page**

<img width="874" height="491" alt="Customer Dashboard — main and only page" src="https://github.com/user-attachments/assets/f2bd5eb9-bb8c-48f9-822a-86eb20b1e952" />

> 📂 **Dashboard file:** `Customer_Dashboard.pbix` — open in **Power BI Desktop** and connect to `Telco-Customer-Churn.csv` if prompted to refresh the data source.

---

## 📌 Business Recommendations

| Priority       | Recommendation                                                                                | Data Basis                                  |
| --------------- | ------------------------------------------------------------------------------------------------ | ---------------------------------------------- |
| 🔴 **Critical**  | Launch a contract-upgrade campaign — incentivize month-to-month customers to switch to annual plans | Month-to-month churn: 42.7% vs. 2.8% for two-year |
| 🔴 **Critical**  | Strengthen onboarding for new customers — welcome offers, proactive engagement in the first year   | Avg. tenure of churned customers: 18 months     |
| 🟠 **High**      | Encourage electronic check users to switch to auto-pay methods                                     | Electronic check churn: 45.3% vs. ~15–19% for other methods |
| 🟠 **High**      | Investigate fiber optic service quality, pricing, and support experience                            | Fiber optic churn: 41.9% vs. DSL 19.0%          |
| 🟡 **Medium**    | Design a Senior Citizen retention offer (simplified plans, dedicated support)                      | Senior churn: 41.7% vs. 23.6% for non-seniors   |
| 🟢 **Low**       | Re-evaluate pricing/value perception for higher-paying customers                                    | Churned customers pay ~$13/month more on average|

---

## ⚠️ Limitations

- **Single snapshot, not time-series** — this is a point-in-time dataset; there's no month-by-month churn trend, only tenure at the time of the snapshot.
- **Correlation, not causation** — insights on Fiber Optic and Electronic Check show strong association with churn, not a proven root cause.
- **No explicit Churn Rate KPI card** — the dashboard shows raw churned counts; churn rate (26.54%) is calculated but not yet a headline card.
- **Public benchmark dataset** — no complaint logs, support tickets, or competitor data to explain *why* segments churn more, only *that* they do.

---

## 🚀 Future Scope

- **🤖 Predictive ML Model** — extend to a classification model (Logistic Regression, Random Forest) to flag at-risk customers before they churn
- **📊 Churn Rate KPI Card** — add churn rate (%) directly to the dashboard, dynamic with the existing Senior Citizen slicer
- **🎛️ More Slicers** — extend interactivity to Contract Type and Internet Service, the two strongest churn drivers
- **🧠 Customer Lifetime Value (CLV)** — combine churn risk with revenue data to prioritize retention spend on high-value customers
- **📬 Complaint/Support Data** — incorporate support ticket data to move from correlation to a clearer causal story

---

## 📁 Folder Structure

```
telco-customer-churn-analysis/
│
├── Telco-Customer-Churn.csv       # Raw dataset (7,043 rows × 21 cols)
├── churn_analysis.ipynb           # Data cleaning & EDA notebook
├── Customer_Dashboard.pbix        # Power BI dashboard (single page)
└── README.md                      # Project documentation
```

---

## ▶️ How to Run

### Prerequisites

- Python 3.8 or above
- Power BI Desktop ([download here](https://powerbi.microsoft.com/desktop/))
- Jupyter Notebook or JupyterLab

### Step 1 — Clone the Repository

```
git clone https://github.com/akarshitaaaa/Telco-Customer-Churn-Analysis.git
cd Telco-Customer-Churn-Analysis
```

### Step 2 — Set Up Python Environment

```
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate

pip install pandas numpy matplotlib seaborn jupyter
```

### Step 3 — Run the Notebook

```
jupyter notebook churn_analysis.ipynb
```

Run all cells in order. The notebook will:
1. Load and inspect `Telco-Customer-Churn.csv`
2. Fix the `TotalCharges` data type and map `SeniorCitizen` values
3. Generate all EDA visualizations (countplots, pie chart, tenure histogram, contract/payment breakdowns, service-type subplots)

### Step 4 — Open the Power BI Dashboard

1. Launch **Power BI Desktop**
2. Open `Customer_Dashboard.pbix`
3. If prompted, go to **Transform data → Data source settings** and re-point to `Telco-Customer-Churn.csv`
4. Click **Refresh** to reload the visuals

---

## ✅ Conclusion

This project delivers a data-driven picture of customer churn in the telecom industry using a single, focused Power BI dashboard. With **7,043 customers** and **21 features**, the analysis shows that **contract type, tenure, payment method, and internet service type** are the strongest levers for reducing the current **26.54% churn rate**.

The two highest-impact opportunities — moving month-to-month customers onto longer contracts, and strengthening the first-year onboarding experience — are the most actionable starting points for retention efforts.

---

**⭐ If you found this project useful, please give it a star!**

Built with Python & Power BI
