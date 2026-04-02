# Superstore Sales Analytics

![SQL](https://img.shields.io/badge/SQL-MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-Dashboard-E97627?style=flat&logo=tableau&logoColor=white)
![Dataset](https://img.shields.io/badge/Records-9%2C994-2ecc71?style=flat)
![Years](https://img.shields.io/badge/Period-2014--2017-blue?style=flat)

## About This Project

This is a **learning project** built to practice the full workflow of SQL data cleaning followed by Tableau visualization. I took the raw Superstore dataset, cleaned and explored it using MySQL, then connected the cleaned data to Tableau Professional Desktop to build interactive sales dashboards.

The project was also shared on [LinkedIn](https://www.linkedin.com/posts/datta-sai22_dataanalytics-sql-tableau-ugcPost-7351908318535184384-qL8f).

---

## What I Did

### 1. Data Cleaning & Preparation (MySQL)
- Imported the raw Superstore CSV into MySQL
- Cleaned column types, handled inconsistent date formats using `DATEPARSE`
- Created a `cleaned_orders` table used as the Tableau data source
- Calculated `Profit Margin` as a derived column

### 2. Calculated Fields in Tableau

| Field | Logic |
|---|---|
| Total Sales | SUM of Sales |
| Month Name | DATEPARSE on Order Date string |
| Month Across Years | Month name + Year (for trend axis) |
| Order Year | YEAR() extracted from Order Date |
| Discount Highlight | IF Discount = 0.2 THEN "Highlight" ELSE "Normal" |
| Label Losses | IF Profit < 0 THEN "Loss" ELSE "Profit" |
| Profit Margin | Pre-calculated in MySQL, used in Tableau |

### 3. Dashboards Built (3 Dashboards)
- **Dashboard 1** — Sales overview: KPIs, monthly trend, category breakdown, top customers
- **Dashboard 2** — Discount & profitability analysis: discount impact chart, loss-making orders, sub-category profit
- **Dashboard 3** — Additional views: scatter plot, order volume trends

**Worksheets included:** KPI cards, line charts (monthly & order month), bar charts (category, sub-category, region), horizontal bar, scatter plot, discount highlight chart, profit/loss labelled view

---

## Dataset

| Property | Detail |
|---|---|
| Source | Sample Superstore (Tableau built-in dataset) |
| Records | 9,994 orders |
| Period | January 2014 – December 2017 |
| Columns | Order ID, Order Date, Ship Mode, Customer, Segment, Region, Category, Sub-Category, Sales, Quantity, Discount, Profit |

> The dataset is included in this repo as `sample_superstore.csv` — it is a well-known public dataset widely used for analytics practice.

---

## Key Findings

### 1. Discounts are hurting profitability
Orders **with** a discount averaged **-$6.66 profit**.
Orders **without** a discount averaged **+$66.90 profit**.
That is a $73 difference per order — heavy discounting is the single biggest driver of losses.

### 2. Furniture has a very low profit margin (2.5%)
| Category | Total Sales | Total Profit | Margin |
|---|---|---|---|
| Technology | ~$836K | ~$145K | 17.4% |
| Office Supplies | ~$719K | ~$122K | 17.0% |
| Furniture | ~$742K | ~$18K | **2.5%** |

Furniture generates similar sales to other categories but barely any profit.

### 3. Nearly 1 in 5 orders is loss-making
1,871 out of 9,994 orders (18.7%) recorded negative profit — largely driven by discounted Furniture and some Technology items.

### 4. Consistent sales growth year on year
Order volume grew from 1,993 orders in 2014 to 3,312 in 2017 — showing steady business growth across the 4-year period.

---

## Tools Used

| Tool | Purpose |
|---|---|
| MySQL | Data cleaning and preparation |
| Tableau Professional Desktop | Calculated fields, charts, dashboards |

---

## Repository Structure

```
superstore-sales-analytics/
│
├── data/
│   └── sample_superstore.csv          # Raw dataset
│
├── sql/
│   └── superstore_cleaning.sql        # SQL cleaning queries
│
├── dashboard/
│   └── sales_DB.twb                   # Tableau workbook
│
└── README.md
```

---

## How to Open

**Tableau Dashboard:**
1. Open `sales_DB.twb` in Tableau Desktop
2. If prompted to reconnect, point the data source to your local MySQL database or the CSV file
3. All calculated fields are embedded in the workbook

---

## What I Learned

- Full workflow from raw CSV → SQL cleaning → Tableau visualization
- Writing date parsing and string manipulation in Tableau calculated fields
- How to highlight specific data points (discount = 20%) using conditional calculated fields
- How discounting strategy directly impacts profitability — a real business insight
- Building multi-dashboard Tableau workbooks with cross-sheet filters and actions

---

## Connect

**Vadla Datta Sai**
Aspiring Data Analyst | Hyderabad, India
[LinkedIn](https://www.linkedin.com/in/datta-sai22)
