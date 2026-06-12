# 📊 Sales Performance & Data Quality Analysis

End-to-end data analysis project focused on **sales performance**, **profitability**, **returns**, and **data quality assessment** for a simulated retail company.

This project combines **Python-based exploratory data analysis**, **data cleaning**, **business KPI analysis**, and an **interactive Power BI dashboard** published through GitHub Pages.

---

## 🔗 Project Links

- [Interactive Power BI Dashboard](https://davidlafuentem.github.io/BI_SALES_ANALYSIS/dashboard/)
- [Jupyter Notebook](./notebooks/Final_financial_EDA.ipynb)
- [Dashboard Files](./dashboard/)
- [Data Folder](./data/)

---

## 🧭 Business Context

This analysis simulates a retail company aiming to improve its sales performance and profitability.

The project focuses on understanding how revenue and profit are distributed across products, regions, and salespeople, while also identifying data quality issues that could affect business decision-making.

---

## ❓ Business Questions

The project addresses the following business questions:

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

The main objectives of this project are:

- Explore and understand the structure of the sales dataset.
- Detect and assess data quality issues.
- Clean and standardize inconsistent categorical values.
- Evaluate whether missing values can be reliably imputed.
- Build reliable subsets for different analytical purposes.
- Calculate key business KPIs.
- Identify insights related to revenue, profit, returns, and sales distribution.
- Create an interactive Power BI dashboard to support business exploration.

---

## 🗂️ Dataset Overview

The dataset contains sales transactions for a simulated retail business.

Main fields include:

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

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Jupyter Notebook**
- **Power BI**
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
│   ├── Sales_Dataset_2024 (1).xlsx
│   └── sales_clean.csv
├── notebooks/
│   └── Final_financial_EDA.ipynb
└── README.md
```

---

## 🔎 Methodology

### 1. Data Loading and Initial Exploration

The dataset was loaded into Python using Pandas.

The initial exploration included:

- Dataset dimensions
- Column types
- Missing values
- Descriptive statistics
- Initial inspection of categorical values
- Detection of negative financial values

---

### 2. Data Quality Assessment

Several data quality issues were identified:

- Missing values in `Region`, `Product`, `Salesperson`, `Units_Sold`, `Unit_Price`, `Revenue`, `Cost`, and `Profit`
- Inconsistent product names, such as different capitalization and misspellings
- Inconsistent region names, such as different capitalization and spelling errors
- Negative values in financial fields, requiring business interpretation

Negative transactions were analyzed and interpreted as **product returns**, because `Units_Sold`, `Revenue`, `Cost`, and `Profit` were consistently negative in those records.

---

### 3. Data Cleaning

The cleaning process included:

- Standardizing product names
- Correcting known product name errors
- Standardizing region names
- Correcting known region name errors
- Reviewing missing values
- Validating whether imputation was reliable
- Creating analysis-specific subsets

Product and region values were cleaned to avoid incorrect aggregation caused by spelling or formatting inconsistencies.

---

### 4. Missing Values Strategy

Missing values were not automatically removed or imputed without validation.

The analysis evaluated whether missing values could be inferred from existing patterns in the data.

Key conclusions:

- Missing `Region` values could not be reliably imputed from salesperson behavior.
- Missing `Product` values could not be reliably imputed from salesperson behavior.
- Missing financial values could not be reconstructed using fixed product prices, because product prices were not constant across transactions.

As a result, two specialized subsets were created:

| Subset | Purpose |
|---|---|
| `df_dimensional` | Used for product, region, and salesperson distribution analysis |
| `df_financial` | Used for revenue, cost, profit, margin, and returns analysis |

This approach avoids unnecessary data loss while keeping each type of analysis reliable.

---

### 5. Feature Engineering

A new feature was created:

| Feature | Description |
|---|---|
| `Transaction_Type` | Classifies transactions as `Sale` or `Refund` |

Transactions with negative `Revenue`, `Cost`, and `Profit` were classified as **Refunds**. All other valid transactions were classified as **Sales**.

This allowed product returns to be analyzed separately from regular sales.

---

## 📈 Key Business Metrics

| Metric | Result |
|---|---:|
| Total Revenue | `$20,719,567.00` |
| Total Profit | `$5,225,307.07` |
| Profit Margin | `25.22%` |
| Top Product by Revenue | `Tablet` |
| Top Product Revenue Share | `14.14%` |
| Top Region by Revenue | `West` |
| Top Region Revenue Share | `27.02%` |
| Top Salesperson by Revenue | `Grace` |
| Top Salesperson Revenue Share | `13.63%` |
| Returns Impact on Revenue | `0.07%` |

---

## 💡 Main Insights

### Profitability

The business shows a healthy profitability level, with a profit margin of **25.22%**.

This suggests that the company is generating solid profit after accounting for costs.

---

### Product Performance

Revenue is relatively well distributed across products.

The top-performing product is **Tablet**, contributing **14.14%** of total revenue.

This indicates that the business does not depend excessively on a single product.

---

### Regional Performance

The leading region is **West**, contributing **27.02%** of total revenue.

Although West is the strongest region, the revenue distribution across regions is relatively balanced, reducing the risk of excessive geographical dependency.

---

### Sales Team Performance

The top salesperson is **Grace**, contributing **13.63%** of total revenue.

Sales performance is well distributed across the team, with no single salesperson dominating overall revenue generation.

This suggests a balanced sales structure and lower dependency on individual performance.

---

### Returns Analysis

Returns represent only **0.07%** of total revenue.

This indicates that product returns have a minimal impact on overall business performance.

---

### Sales Volatility

The time series analysis shows a volatile monthly sales pattern.

Although there is some positive growth, the trend is not strong or consistent enough to conclude sustained growth.

Lower-performing months, such as **July** and **March**, may require further investigation to identify whether the pattern is seasonal, operational, or temporary.

---

## ✅ Final Conclusions

The analysis suggests that the business is profitable, diversified, and operationally balanced.

The company does not show strong dependency on a single product, region, or salesperson. Returns are not a major issue, and overall profitability is healthy.

However, sales volatility should be investigated further. The business may benefit from a deeper analysis of seasonality, promotional activity, customer behavior, and external factors affecting monthly performance.

---

## 🚀 Recommendations

Based on the analysis, the recommended next steps are:

- Investigate the causes of monthly sales volatility.
- Analyze whether low-performing months are linked to seasonality or operational factors.
- Explore customer-level data to understand purchasing behavior.
- Develop forecasting models to improve business planning.
- Monitor returns over time, even though their current impact is low.
- Continue using separate analytical datasets when missing values affect different business questions.

---

## 📊 Interactive Power BI Dashboard

An interactive Power BI dashboard was created as a separate deliverable.

The dashboard allows users to explore the main KPIs and business dimensions visually, including:

- Revenue
- Profit
- Profit margin
- Product performance
- Regional performance
- Salesperson performance
- Returns impact
- Monthly trends

The dashboard is published through GitHub Pages and can be accessed here:

[Open Interactive Dashboard](https://davidlafuentem.github.io/BI_SALES_ANALYSIS/dashboard/)

The dashboard complements the Python analysis by providing an interactive way to explore the cleaned and analyzed data.

## ⚠️ Data Quality Note — Unassigned Transactions in Power BI Dashboard

A total of **114 transactions** (5.7% of the dataset) contain missing values 
in at least one categorical field (`Region`, `Product`, or `Salesperson`), 
representing **$1,022,924 in revenue** (4.94% of total revenue).

| Missing Field | Transactions | Revenue Impact |
|---|---|---|
| Region | 39 | $315,402 |
| Product | 40 | $397,339 |
| Salesperson | 40 | $360,943 |

These records could not be reliably imputed based on existing data patterns, 
as confirmed during the Python EDA phase.

To minimise the impact on financial accuracy, custom DAX measures were created 
in the Power BI dashboard to ensure that unassigned transactions are always 
included in financial totals, regardless of the active filters:

- **Total Revenue** always includes the full $20.7M baseline
- **Profit Margin** is calculated over the complete revenue base
- Filtering by `Region`, `Product`, or `Salesperson` never silently 
  excludes unassigned revenue from KPI cards

This approach preserves full financial integrity while allowing clean 
categorical analysis across all dashboard pages.

---

## ▶️ How to Run the Notebook

1. Clone the repository:

```bash
git clone https://github.com/davidlafuentem/BI_SALES_ANALYSIS.git
```

2. Open the project folder:

```bash
cd BI_SALES_ANALYSIS
```

3. Open the Jupyter Notebook:

```bash
jupyter notebook notebooks/Final_financial_EDA.ipynb
```

4. Run the notebook cells in order.

---

## 📦 Project Deliverables

| Deliverable | Description |
|---|---|
| Python Notebook | Exploratory data analysis, cleaning, KPIs, and conclusions |
| Clean Dataset | Processed dataset used for further analysis and dashboarding |
| Power BI Dashboard | Interactive dashboard for business exploration |
| GitHub Pages Site | Static page used to embed the public Power BI dashboard |
| README Documentation | Project summary and portfolio presentation |

---

## 🧠 Skills Demonstrated

This project demonstrates the following skills:

- Exploratory Data Analysis
- Data Cleaning
- Data Quality Assessment
- Missing Value Analysis
- Feature Engineering
- Business KPI Design
- Profitability Analysis
- Returns Analysis
- Time Series Exploration
- Data Storytelling
- Power BI Dashboarding
- GitHub Project Documentation
- GitHub Pages Deployment

---

## 👤 Author

**David Lafuente Martín**

Data Analytics / Business Intelligence Portfolio Project
