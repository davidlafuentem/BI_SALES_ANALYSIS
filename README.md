# 📊 Sales Performance & Data Quality Analysis

End-to-end data analysis project focused on **sales performance**, **profitability**, **returns**, and **data quality assessment** for a simulated retail company.

This project combines **Python-based exploratory data analysis**, **data cleaning**, **business KPI analysis**, and an **interactive Power BI dashboard** published through GitHub Pages.

---

## 🔗 Project Links

- [Interactive Power BI Dashboard](https://davidlafuentem.github.io/BI_SALES_ANALYSIS/dashboard/)
- [Jupyter Notebook](https://github.com/davidlafuentem/BI_SALES_ANALYSIS/blob/main/notebooks/Final_financial_EDA.ipynb)
- [Dashboard Files](https://github.com/davidlafuentem/BI_SALES_ANALYSIS/tree/main/dashboard)
- [Data Folder](https://github.com/davidlafuentem/BI_SALES_ANALYSIS/tree/main/data)

---

## 🧭 Business Context

This analysis simulates a retail company aiming to improve its sales performance and profitability.

The project focuses on understanding how revenue and profit are distributed across products, regions, and salespeople, while also identifying data quality issues that could affect business decision-making.

---

## ❓ Business Questions

- Which products generate the most revenue?
- Which regions contribute the most to sales performance?
- Which salespeople drive the highest revenue?
- What is the overall profitability of the business?
- What is the impact of product returns on revenue?
- Are there data quality issues that could affect the reliability of the analysis?
- Is the business overly dependent on specific products, regions, or salespeople?
- Are there visible monthly sales patterns or volatility?

---

## 🎯 Project Objectives

- Explore and understand the structure of the sales dataset.
- Detect and assess data quality issues.
- Clean and standardize inconsistent categorical values.
- Evaluate whether missing values can be reliably imputed.
- Calculate key business KPIs.
- Identify insights related to revenue, profit, returns, and sales distribution.
- Create an interactive Power BI dashboard to support business exploration.

---

## 🗂️ Dataset Overview

The dataset contains sales transactions for a simulated retail business.

| Column | Description |
|---|---|
| `Date` | Transaction date |
| `Region` | Sales region |
| `Product` | Product sold |
| `Salesperson` | Salesperson responsible for the transaction |
| `Units_Sold` | Number of units sold |
| `Unit_Price` | Unit price of the product |
| `Category` | Product category |
| `Revenue` | Transaction revenue |
| `Cost` | Transaction cost |
| `Profit` | Transaction profit |

The original dataset contains **2,000 rows** and **10 columns**.

---

## 🛠️ Tools & Technologies

- **Python** — Pandas, NumPy, Matplotlib
- **Jupyter Notebook**
- **Power BI Desktop** — DAX, Power Query
- **GitHub Pages**
- **Git / GitHub**

---

## 📁 Repository Structure

```text
BI_SALES_ANALYSIS/
├── dashboard/
│   ├── index.html
│   └── README.md
├── data/
│   ├── Sales_Dataset_2024.xlsx
│   └── sales_clean.csv
├── notebooks/
│   └── Final_financial_EDA.ipynb
└── README.md
```

---

## 🔎 Methodology

### 1. Data Loading and Initial Exploration

The dataset was loaded into Python using Pandas. The initial exploration included dataset dimensions, column types, missing values, descriptive statistics, and detection of negative financial values.

---

### 2. Data Quality Assessment

Several data quality issues were identified:

- Missing values in `Region`, `Product`, `Salesperson`, `Units_Sold`, `Unit_Price`, `Revenue`, `Cost`, and `Profit`
- Inconsistent product and region names due to capitalization and spelling errors
- Negative values in financial fields, interpreted as product returns

---

### 3. Data Cleaning

- Standardizing and correcting product and region names
- Reviewing and validating missing values
- Creating analysis-specific subsets based on data availability

---

### 4. Missing Values Strategy

Missing values were not automatically removed or imputed without validation. The analysis confirmed that missing categorical values (`Region`, `Product`, `Salesperson`) could not be reliably inferred from existing data patterns.

Two analytical subsets were created:

| Subset | Purpose |
|---|---|
| `df_dimensional` | Product, region, and salesperson distribution analysis |
| `df_financial` | Revenue, cost, profit, margin, and returns analysis |

This approach avoids unnecessary data loss while keeping each type of analysis reliable.

---

### 5. Feature Engineering

| Feature | Description |
|---|---|
| `Transaction_Type` | Classifies transactions as `Sale` or `Refund` based on sign of financial fields |

---

## ⚠️ Data Quality Note — Unassigned Transactions

A total of **114 transactions** contain missing values in at least one categorical field, representing **$1,022,924 in revenue** (4.94% of total).

| Missing Field | Transactions | Revenue Impact |
|---|---|---|
| Region | 39 | $315,402 |
| Product | 40 | $397,339 |
| Salesperson | 40 | $360,943 |

These records could not be reliably imputed, as confirmed during the Python EDA phase.

To preserve full financial accuracy in the Power BI dashboard, custom DAX measures were created to ensure unassigned transactions are always included in financial totals regardless of active filters:

- **Total Revenue** always reflects the full $20.7M baseline
- **Profit Margin** is calculated over the complete revenue base
- Filtering by `Region`, `Product`, or `Salesperson` never silently excludes unassigned revenue from KPI cards

---

## 📈 Key Business Metrics

| Metric | Result |
|---|---:|
| Total Revenue | `$20,719,567` |
| Total Profit | `$5,225,307` |
| Profit Margin | `25.22%` |
| Top Product by Revenue | `Tablet` |
| Top Region by Revenue | `West` |
| Top Salesperson by Revenue | `Grace` |
| Returns Impact on Revenue | `0.07%` |

---

## 💡 Main Insights

**Profitability** — The business shows a healthy profit margin of 25.22%, indicating solid cost control.

**Product Performance** — Revenue is well distributed across products. Tablet leads with 14.14% of total revenue, showing no excessive product dependency.

**Regional Performance** — West leads with 27.02% of revenue, but distribution across regions is balanced, reducing geographical risk.

**Sales Team** — Grace is the top performer at 13.63%, but no single salesperson dominates, suggesting a healthy team structure.

**Returns** — Returns represent only 0.07% of revenue, indicating minimal operational impact.

**Sales Volatility** — Monthly revenue shows volatility without a consistent growth trend. Lower-performing months such as July and March may warrant further investigation.

---

## ✅ Final Conclusions

The business is profitable, diversified, and operationally balanced. No critical dependency on a single product, region, or salesperson was identified. Returns are not a concern.

Sales volatility remains the main area for further investigation, potentially linked to seasonality or external factors.

---

## 🚀 Recommendations

- Investigate the causes of monthly sales volatility
- Analyze whether low-performing months relate to seasonality or operational factors
- Explore customer-level data to understand purchasing behavior
- Develop forecasting models to improve planning
- Monitor returns over time despite their currently low impact

---

## 📊 Interactive Power BI Dashboard

An interactive 3-page Power BI dashboard was built as a separate deliverable, covering:

- **Sales Performance** — KPIs, monthly trends, revenue by category and region
- **Product Performance** — Revenue and margin by product and category, Top 5 by units sold
- **Regional Analysis** — Revenue and margin by region, monthly stacked trends, Top 5 sellers

[Open Interactive Dashboard](https://davidlafuentem.github.io/BI_SALES_ANALYSIS/dashboard/)

---

## ▶️ How to Run the Notebook

```bash
git clone https://github.com/davidlafuentem/BI_SALES_ANALYSIS.git
cd BI_SALES_ANALYSIS
jupyter notebook notebooks/Final_financial_EDA.ipynb
```

---

## 📦 Project Deliverables

| Deliverable | Description |
|---|---|
| Python Notebook | EDA, data cleaning, KPIs, and conclusions |
| Clean Dataset | Processed dataset for analysis and dashboarding |
| Power BI Dashboard | Interactive 3-page executive dashboard |
| GitHub Pages Site | Public embed of the Power BI dashboard |
| README | Project summary and portfolio documentation |

---

## 🧠 Skills Demonstrated

Exploratory Data Analysis · Data Cleaning · Data Quality Assessment · Missing Value Analysis · Feature Engineering · Business KPI Design · DAX Measures · Power BI Dashboarding · GitHub Pages Deployment · Data Storytelling

---

## 👤 Author

**David Lafuente Martín**  
Data Analytics / Business Intelligence Portfolio Project
