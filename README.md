# Data Analyst Assessment — E-Commerce Sales Analysis

## Project Overview
End-to-end data analysis project built for the VirtuBox Data Analyst assessment. Uses the
Brazilian E-Commerce Public Dataset by Olist to identify revenue growth opportunities for
business management.

## Business Problem
Management wants to understand which products, customer segments and regions contribute most
to sales, and where the biggest opportunities exist to grow revenue and improve retention.
See `Data_Analyst_Assessment.xlsx` → **Q2** for the full problem statement, business questions
and hypotheses.

## Dataset
- **Source:** Olist Brazilian E-Commerce Public Dataset (Kaggle) — 9 relational CSV files
- **Size:** 99,441 orders, 112,650 order items, ~93,000 unique customers (2016–2018)
- Details in `Data_Analyst_Assessment.xlsx` → **Q1**

## Data Processing
Cleaned and merged with Python/Pandas: removed duplicates, corrected date types, translated
product categories, handled missing values, filtered to delivered orders for core revenue
analysis, and engineered fields (revenue, delivery time, delivery delay, freight %, monthly
period). Full explanation in **Q3**; full code in `notebook/data_analysis.ipynb`.

## Analysis
Exploratory and business analysis covering revenue by category/state/time, product
units-vs-revenue comparison, customer concentration and repeat-purchase rate, and delivery
performance vs review score. Charts in `dashboard/dashboard_screenshots/` and inline in the
notebook.

## Key Findings
1. Top 10 of ~74 product categories drive **62.4%** of total revenue.
2. **São Paulo (SP)** alone accounts for **~38%** of revenue.
3. Only **5 of the top 10** best-selling products (by units) are also top-10 by revenue.
4. Only **3.0%** of customers are repeat buyers.
5. Late deliveries correlate with a sharp review-score drop (4.20 → 2.24 average).

Full Insight → Evidence → Business Impact → Recommendation table: **Q4**. Surprising finding
deep-dive: **Q5**. Data limitations: **Q6**.

## Recommendations
1. Launch a repeat-purchase incentive after first delivery.
2. Tighten delivery-date accuracy and monitor on-time rate by state/carrier.
3. Invest in targeted marketing/fulfillment in RJ, MG and RS to reduce São Paulo dependency.

Full detail (owner, expected outcome, success metric, priority): **Q7**.

## Dashboard
A Google Looker Studio dashboard should be built from `data/processed_data_delivered.csv`
(or the Google Sheet version) with: Executive KPI summary, revenue trend, category/region
breakdown, top-products table, and filters for Year/Month/State/Category. See
**Q8** in the workbook for the explanation template to fill in once built, and static
reference charts in `dashboard/dashboard_screenshots/`.


## DashBoard link
https://datastudio.google.com/reporting/7046cfb7-e220-4320-a6cc-46764ed82b10

## Files / Folders
```
data-analyst-assessment/
├── README.md
├── Data_Analyst_Assessment.xlsx      # Data, Q1, Q2, Processed Data, Q3-Q8, Q10
├── data/
│   ├── olist_*.csv                   # 9 raw source files
│   ├── processed_data_full.csv       # cleaned & merged, all order statuses
│   └── processed_data_delivered.csv  # cleaned & merged, delivered orders only
├── notebook/
│   └── data_analysis.ipynb           # full cleaning + analysis pipeline, executed
├── dashboard/
│   └── dashboard_screenshots/        # chart1-5 PNGs (category, state, trend, delivery, freight)
└── presentation/
    └── management_presentation.pptx  # 8-slide management deck
```

## How to Run the Python Notebook
```bash
pip install pandas numpy matplotlib seaborn
jupyter notebook notebook/data_analysis.ipynb
```
Run all cells from top to bottom; the notebook reads the 9 raw CSVs from the same folder
(copy them alongside the notebook, or adjust the paths at the top).

## AI Usage
See **Q10** in the workbook: which AI tool was used, what for, one example where it helped
(the payments/reviews aggregation-before-merge step), and one example where its output was
verified and corrected (filtering to delivered-only orders for revenue).
