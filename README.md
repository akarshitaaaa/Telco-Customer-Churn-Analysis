# 📡 Telco Customer Churn Analysis — Python & Power BI

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Analysis-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

*An end-to-end customer churn analysis project — from raw data cleaning to an interactive Power BI dashboard — built to uncover why customers leave and what keeps them.*

</div>

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
- [Future Scope](#-future-scope)
- [Folder Structure](#-folder-structure)
- [How to Run](#️-how-to-run)
- [Conclusion](#-conclusion)

---

## 🧩 Project Overview

Customer churn is one of the most expensive problems in the telecom industry — retaining an existing customer costs far less than acquiring a new one. This project performs a **complete data analysis pipeline** on a real telecom dataset to identify *who* is churning, *why* they are leaving, and *what* can be done to keep them.

The project combines **Python (Pandas, NumPy, Matplotlib, Seaborn)** for data cleaning, EDA, and visualizations with a **Power BI Customer Dashboard** featuring interactive charts, KPI cards, slicers, and Q&A capabilities — delivering business-ready insights for stakeholders.

---

## 💼 Business Problem Statement

> *A telecom company has a churn rate of **26.54%** — more than 1 in 4 customers are leaving. The business needs to understand the key drivers of churn, identify the highest-risk customer segments, and develop targeted strategies to improve customer retention and protect revenue.*

---

## 🎯 Objectives

- ✅ Clean and preprocess the raw dataset (fix data types, handle missing values, encode features)
- ✅ Perform Exploratory Data Analysis (EDA) across all 21 features
- ✅ Identify customer segments with the highest churn rates
- ✅ Visualize churn patterns using Python (Matplotlib & Seaborn)
- ✅ Build an interactive **Customer Dashboard** in Power BI with slicers, KPI cards, and Q&A
- ✅ Translate findings into concrete, prioritized business recommendations

---

## 📊 Dataset Description

**File:** `Telco-Customer-Churn.csv`
**Records:** 7,043 customers &nbsp;|&nbsp; **Features:** 21 columns &nbsp;|&nbsp; **Target:** `Churn` (Yes / No)

| # | Column | Type | Description |
|---|--------|------|-------------|
| 1 | `customerID` | Categorical | Unique customer identifier |
| 2 | `gender` | Categorical | Male / Female |
| 3 | `SeniorCitizen` | Binary | 1 = Senior, 0 = Non-Senior (mapped to Yes/No in analysis) |
| 4 | `Partner` | Categorical | Whether the customer has a partner |
| 5 | `Dependents` | Categorical | Whether the customer has dependents |
| 6 | `tenure` | Numerical | Months the customer has been with the company |
| 7 | `PhoneService` | Categorical | Phone service subscription |
| 8 | `MultipleLines` | Categorical | Multiple phone lines |
| 9 | `InternetService` | Categorical | DSL / Fiber optic / No |
| 10 | `OnlineSecurity` | Categorical | Online security add-on |
| 11 | `OnlineBackup` | Categorical | Online backup add-on |
| 12 | `DeviceProtection` | Categorical | Device protection add-on |
| 13 | `TechSupport` | Categorical | Tech support add-on |
| 14 | `StreamingTV` | Categorical | TV streaming subscription |
| 15 | `StreamingMovies` | Categorical | Movie streaming subscription |
| 16 | `Contract` | Categorical | Month-to-month / One year / Two year |
| 17 | `PaperlessBilling` | Categorical | Paperless billing enabled |
| 18 | `PaymentMethod` | Categorical | Electronic check / Mailed check / Bank transfer / Credit card |
| 19 | `MonthlyCharges` | Numerical | Monthly billing amount (USD) |
| 20 | `TotalCharges` | Numerical | Total amount billed (originally string — fixed in preprocessing) |
| 21 | `Churn` | Binary (Target) | Whether the customer churned: **Yes (1,869) / No (5,174)** |

> **Data Quality Note:** `TotalCharges` contained 11 blank string entries — replaced with `"0"` and cast to `float`. `SeniorCitizen` (0/1) was mapped to `Yes/No` for readability.

---

## 🛠️ Technologies Used

| Tool / Library | Version | Purpose |
|---|---|---|
| 🐍 **Python** | 3.10+ | Core programming language |
| 🐼 **Pandas** | 1.5+ | Data loading, cleaning, transformation |
| 🔢 **NumPy** | 1.23+ | Numerical operations |
| 📊 **Matplotlib** | 3.6+ | Base plotting and chart rendering |
| 🎨 **Seaborn** | 0.12+ | Statistical visualizations (countplots, histplots) |
| 📈 **Power BI Desktop** | Latest | Interactive dashboard with KPI cards, slicers, Q&A |
| 📓 **Jupyter Notebook** | 1.0+ | Development, analysis, and presentation |

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
│  STEP 2: Data Cleaning   │  Fix TotalCharges dtype (str → float)
│  & Preprocessing         │  Map SeniorCitizen 0/1 → Yes/No
│                          │  Verify nulls, check duplicates
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│   STEP 3: EDA &          │  Churn distribution (count + pie chart)
│   Visualizations         │  Churn by: Gender, SeniorCitizen, Tenure,
│   (Python)               │  Contract, PaymentMethod, InternetService,
│                          │  and 9 service-type subplots
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│   STEP 4: Power BI       │  Customer Dashboard (1 main page)
│   Dashboard              │  + Q/A Page + T1 (MonthlyCharges trend)
│   Customer_Dashboard     │  + T2 (Tenure by Contract)
│   .pbix                  │  KPI Cards, Pie Charts, Bar Charts,
│                          │  Line Charts, Funnel, Slicer
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

All figures are derived directly from the dataset (`Telco-Customer-Churn.csv`).

### 1. 📋 Contract Type is the #1 Churn Driver

| Contract | Churn Rate |
|----------|-----------|
| Month-to-month | **42.7%** |
| One year | 11.3% |
| Two year | **2.8%** |

Customers on month-to-month contracts are **15× more likely to churn** than two-year contract holders. This is the single strongest predictor in the dataset.

---

### 2. ⏳ New Customers Churn at Nearly 5× the Rate of Long-Tenured Ones

| Tenure Band | Churn Rate |
|-------------|-----------|
| 0 – 12 months | **47.7%** |
| 13 – 24 months | 28.7% |
| 25 – 48 months | 20.4% |
| 49 – 72 months | **9.5%** |

Average tenure of churned customers is **18.0 months** vs. **37.6 months** for retained customers. The first year is the most critical retention window.

---

### 3. 💳 Electronic Check Users Have the Highest Churn Rate

| Payment Method | Churn Rate |
|----------------|-----------|
| Electronic check | **45.3%** |
| Mailed check | 19.1% |
| Bank transfer (automatic) | 16.7% |
| Credit card (automatic) | **15.2%** |

Electronic check users churn at **3× the rate** of auto-payment users, suggesting lower engagement and commitment.

---

### 4. 🌐 Fiber Optic Users Churn at More Than Twice the Rate of DSL

| Internet Service | Churn Rate |
|-----------------|-----------|
| Fiber optic | **41.9%** |
| DSL | 19.0% |
| No internet service | 7.4% |

Despite being a premium product, fiber optic has the highest churn — likely driven by higher monthly charges and unmet service quality expectations.

---

### 5. 👴 Senior Citizens Churn at Nearly Double the Rate

| Segment | Churn Rate |
|---------|-----------|
| Non-Senior (0) | 23.6% |
| Senior Citizen (1) | **41.7%** |

Senior citizens make up only 16.2% of the customer base but represent a disproportionately high churn segment.

---

### 6. 💰 Churned Customers Have Significantly Higher Monthly Charges

| Churn Status | Avg Monthly Charges |
|-------------|-------------------|
| Retained (No) | $61.27 |
| Churned (Yes) | **$74.44** |

Churned customers pay **$13.17/month more** on average — pointing to pricing sensitivity and perceived value gap as key churn contributors.

---

### 7. ⚧ Gender Has Minimal Impact on Churn

| Gender | Churn Rate |
|--------|-----------|
| Female | 26.9% |
| Male | 26.2% |

Churn rates are nearly identical across genders — gender is not a meaningful segmentation variable for retention campaigns.

---

## 📊 Power BI Dashboard

The **Customer Dashboard** (`Customer_Dashboard.pbix`) is a single-file interactive report with **4 pages**:

### Dashboard Pages

| Page | Purpose |
|------|---------|
| **Dashboard** | Main overview — KPI cards, pie charts, bar/column charts, line chart, funnel visuals, and Senior Citizen card |
| **Q/A** | Natural language Q&A visual for ad-hoc queries by business users |
| **T1** | Monthly Charges trend line broken down by Contract type |
| **T2** | Tenure distribution clustered by Contract type |

### Visuals Included on the Dashboard Page

- 🃏 **KPI Cards** — Total Customers count, Senior Citizen count
- 🥧 **Pie Charts** — Customer split by Internet Service, Customer split by Contract type
- 📊 **Column Charts** — Customer count by Gender (with Churn hue)
- 📉 **Clustered Bar Chart** — Customers by Payment Method
- 📈 **Line Chart** — Customer count by Tenure
- 🔺 **Funnel Chart** — Customer split by Partner status
- 🎛️ **Slicer** — Filter the entire dashboard by Senior Citizen status

### Dashboard Preview

> **Main Dashboard Page**

![Dashboard Main Page](<img width="1309" height="731" alt="image" src="https://github.com/user-attachments/assets/16a2d34a-614f-4a74-82eb-8101e9fbcb6f" />
)
*← Add your Power BI screenshot here*


> 📂 **Dashboard file:** `Customer_Dashboard.pbix`
> Open in **Power BI Desktop** → connect to `Telco-Customer-Churn.csv` if prompted to refresh the data source.

---

## 📌 Business Recommendations

| Priority | Recommendation | Data Basis | Target Segment |
|---|---|---|---|
| 🔴 **Critical** | Launch a **contract upgrade campaign** — offer discounts to move month-to-month customers to annual contracts | M-t-M churn: 42.7% vs 2.8% for 2-yr | Month-to-month customers |
| 🔴 **Critical** | Implement a **60-day onboarding program** — proactive check-ins, tutorials, and a dedicated success contact in the first 2 months | 47.7% churn rate in first year | Tenure < 12 months |
| 🟠 **High** | Run **auto-payment enrollment drives** — email/SMS campaigns incentivizing switch from electronic check to auto-pay | E-check churn: 45.3% vs ~16% for auto-pay | Electronic check users |
| 🟠 **High** | Investigate **fiber optic service quality** — survey churned fiber customers and review pricing vs. DSL | Fiber churn: 41.9% vs DSL 19.0% | Fiber optic subscribers |
| 🟡 **Medium** | Create a **Senior Citizen care tier** — simplified plans, lower-cost options, dedicated support line | Senior churn: 41.7% vs 23.6% | SeniorCitizen = Yes |
| 🟡 **Medium** | Introduce **loyalty rewards at the 12-month milestone** to break through the highest-risk tenure window | Churn drops from 47.7% → 28.7% after month 12 | Tenure 9–12 months |
| 🟢 **Low** | Re-evaluate **pricing strategy for high-charge customers** — consider value-add bundles vs. price reductions | Churned customers pay $13.17/mo more on average | MonthlyCharges > $70 |

---

## 🚀 Future Scope

- **🤖 Predictive ML Model** — Train classification models (Logistic Regression, Random Forest, XGBoost) to predict individual churn probability and generate a customer risk score, enabling proactive outreach before churn occurs

- **⚙️ Real-Time Scoring API** — Deploy the trained model as a REST API (FastAPI / Flask) to score new customers daily and feed risk scores back into the CRM system

- **🧠 Customer Lifetime Value (CLV) Integration** — Combine churn probability with revenue data to prioritize retention spend on high-value at-risk customers rather than treating all churners equally

- **📬 Automated Retention Triggers** — Use Power Automate or Python scheduling to send alerts to account managers when a customer's predicted churn probability exceeds a defined threshold

- **📊 Advanced Power BI AI Visuals** — Add the **Key Influencers** and **Decomposition Tree** visuals to the dashboard so non-technical stakeholders can explore churn drivers interactively without SQL or Python

- **🌐 NLP on Customer Feedback** — Apply sentiment analysis to support call logs or customer reviews to surface qualitative churn drivers that structured data alone cannot capture

- **📅 Survival / Cohort Analysis** — Use Kaplan-Meier survival curves and cohort-based analysis to model churn timing more precisely across different customer acquisition cohorts

- **☁️ Power BI Service Deployment** — Publish the dashboard to Power BI Service for organization-wide sharing, scheduled data refresh, and row-level security by business unit

---

## 📁 Folder Structure

```
telco-customer-churn-analysis/
│
├── 📂 data/
│   └── Telco-Customer-Churn.csv          # Raw dataset (7,043 rows × 21 cols)
│
├── 📂 notebooks/
│   └── churn_analysis.ipynb              # Full EDA & visualization notebook
│
├── 📂 powerbi/
│   └── Customer_Dashboard.pbix           # Power BI dashboard (4 pages)
│
├── 📂 assets/
│   └── screenshots/
│       ├── dashboard_main.png            # Main dashboard screenshot
│       ├── dashboard_T1_monthly_charges.png
│       ├── dashboard_T2_tenure.png
│       └── dashboard_QA.png
│
├── 📄 requirements.txt                   # Python dependencies
└── 📄 README.md                          # Project documentation
```

---

## ▶️ How to Run

### Prerequisites
- Python 3.8 or above
- Power BI Desktop (free — [download here](https://powerbi.microsoft.com/desktop/))
- Jupyter Notebook or JupyterLab

---

### Step 1 — Clone the Repository

```bash
git clone https://github.com/your-username/telco-customer-churn-analysis.git
cd telco-customer-churn-analysis
```

### Step 2 — Set Up Python Environment

```bash
# Create and activate a virtual environment
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

**`requirements.txt`**
```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
```

### Step 3 — Run the Notebook

```bash
jupyter notebook notebooks/churn_analysis.ipynb
```

Run all cells in order. The notebook will:
1. Load and inspect `Telco-Customer-Churn.csv`
2. Fix the `TotalCharges` data type and map `SeniorCitizen` values
3. Generate all EDA visualizations (countplots, pie charts, histograms, stacked bars, subplots)

### Step 4 — Open the Power BI Dashboard

1. Launch **Power BI Desktop**
2. Open `Customer_Dashboard.pbix`
3. If prompted, click **Transform data → Data source settings** and re-point to `data/Telco-Customer-Churn.csv`
4. Click **Refresh** to reload the visuals
5. Explore all 4 pages: **Dashboard**, **Q/A**, **T1**, **T2**

---

## ✅ Conclusion

This project delivers a complete, data-driven picture of customer churn in the telecom industry. With a dataset of **7,043 customers** and **21 features**, the analysis pinpoints that **contract type, customer tenure, payment method, and internet service type** are the four most actionable levers for reducing the 26.54% churn rate.

The combination of Python-based EDA and a multi-page Power BI dashboard means both technical analysts and business stakeholders can explore the findings at their own level — from raw visualizations in a Jupyter notebook to interactive slicers and Q&A in Power BI.

The most immediate opportunities — converting month-to-month customers to annual contracts and improving the first-year onboarding experience — alone could dramatically shift retention numbers without requiring large infrastructure investments.

---

<div align="center">

**⭐ If you found this project useful, please give it a star!**

Built with ❤️ using Python & Power BI

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username)

</div>
