# 📈 Retail Sales Data Analysis & Interactive Dashboard

> A full data analysis project — from raw, unstructured sales data to an interactive Tableau dashboard that enabled real business decisions.

---

## 🔍 Problem Statement

A retail business had accumulated two years of sales data spread across multiple spreadsheets. There was no visibility into which products were underperforming, no regional breakdown, and no way to track targets month-on-month. Management was making stock and budget decisions without data to back them.

This project turned that raw data into a clear, actionable dashboard.

---

## 🎯 Project Objectives

- Clean and consolidate two years of messy sales data
- Identify top-performing and underperforming products and regions
- Build an interactive dashboard for ongoing monthly KPI tracking
- Deliver written recommendations based on the analysis findings

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Excel / Power Query | Data cleaning and transformation |
| SQL (MySQL) | Data aggregation and querying |
| Python (Pandas, Matplotlib) | Exploratory analysis and visualisation |
| Tableau | Interactive dashboard creation |

---

## 📁 Dataset

- **Type:** Retail sales records (client data — anonymised)
- **Period:** 2 years of monthly transaction data
- **Fields include:** Date, Region, Product Category, Product Name, Units Sold, Revenue, Target Revenue, Sales Rep

---

## 🔄 Process

### Step 1 — Data Cleaning (Power Query & Python)
- Removed duplicate transaction records
- Fixed inconsistent date formats and region name spelling variations
- Filled missing product category values using product name lookup
- Standardised currency values and removed formatting characters
- Validated totals against source documents

### Step 2 — SQL Aggregation
```sql
-- Example: Regional revenue vs target
SELECT
  region,
  SUM(revenue) AS total_revenue,
  SUM(target_revenue) AS total_target,
  ROUND((SUM(revenue) - SUM(target_revenue)) / SUM(target_revenue) * 100, 2) AS variance_pct
FROM sales_data
GROUP BY region
ORDER BY variance_pct ASC;
```

Other queries written:
- Monthly revenue trend by region
- Top 10 products by revenue
- Bottom 10 products by units sold
- Sales rep performance ranking
- Year-on-year growth by product category

### Step 3 — Python Exploratory Analysis (Pandas/Matplotlib)
- Correlation between units sold and revenue by region
- Seasonal trends across the two-year period
- Product performance distribution (Pareto analysis — 80/20 rule)

### Step 4 — Tableau Dashboard
Built an interactive dashboard with:
- **KPI cards:** Total Revenue, Revenue vs Target, Growth Rate, Units Sold
- **Bar chart:** Revenue by Region with target line overlay
- **Line chart:** Monthly revenue trend (Year 1 vs Year 2)
- **Tree map:** Revenue by Product Category
- **Table:** Bottom 10 underperforming products
- **Filters:** Region, Product Category, Date Range

---

## 📈 Key Findings

- **North region** consistently underperformed targets by 18% — linked to low sales rep activity, not low demand
- **3 product categories** accounted for 74% of total revenue (Pareto confirmed)
- Revenue dipped every **August and December** — indicating seasonal patterns not previously accounted for in targets
- **Top 5 products** drove 61% of units sold but only 38% of revenue — pricing review flagged
- Year-on-year growth: **+9.3%** overall, but concentrated in only 2 regions

---

## 💡 Recommendations Delivered

1. Reallocate sales rep resources to the North region for Q3
2. Adjust seasonal targets for August and December to reflect realistic demand cycles
3. Review pricing strategy for high-volume, low-revenue products
4. Focus marketing spend on the top 3 product categories driving 74% of revenue
5. Set region-specific growth targets rather than a single national figure

---

## 📊 Results & Impact

| Metric | Outcome |
|---|---|
| Regional sales improvement | ⬆️ 12% after recommendations implemented |
| Monthly reporting time | ⬇️ 50% reduction |
| KPI visibility | Business now tracks performance monthly vs previously quarterly |

---

## 📸 Dashboard Preview

![Retail-Sales-Dashboard](images/Screenshot.png)
---

## 🚀 How to Explore

1. Download the Excel data file and `.twbx` Tableau workbook from this repository
2. Open the Tableau workbook in Tableau Desktop or Tableau Public
3. Use the region and category filters to explore performance breakdowns
4. Review `analysis_report.pdf` for the full written findings and recommendations

---

## 🔮 Future Improvements

- Connect to a live database for real-time dashboard updates
- Add customer segmentation analysis (RFM model)
- Build a Python forecast model for next-quarter revenue prediction

---

## 👤 Author

**Agboola Anuoluwapo David**
Data Analyst | Web Developer | CS Graduate

- 🌐 Portfolio: [yahwehboi.github.io](https://yahwehboi.github.io)
- 💼 LinkedIn: [linkedin.com/in/anuoluwapo-agboola-b11000195](https://linkedin.com/in/anuoluwapo-agboola-b11000195)
- 📧 agboolaanouluwapo@gmail.com

---

## 📄 License

MIT License — free to use for educational and portfolio purposes.
