---

# Vendor Performance Analysis

> An end-to-end data analytics project uncovering vendor and brand profitability insights for retail & wholesale businesses.  
> Built with **Python, SQL (SQLite), and Power BI**.


---

## Business Problem

Retail & wholesale companies often face:

* High capital locked in slow-moving or stuck inventory  
* Inefficient vendor pricing and dependency risks  
* Difficulty identifying profitable vs. underperforming vendors  

**Goal:** Optimize vendor relationships, improve margins, and reduce holding costs through **data-driven insights**.

---

## Objectives

* Identify **top-performing vendors** and **underperforming brands**  
* Highlight **stuck inventory** tying up capital  
* Detect **pricing mismatches** and margin leakages  
* Analyze **bulk purchase impact** on unit costs  
* Provide actionable insights via an **interactive dashboard**

---

## Workflow

1. **Data Ingestion** → Load CSVs into SQLite using Python (with logging & error handling)  
2. **EDA & Cleaning** → Explore, validate, and clean data using Pandas + SQL  
3. **Analysis** → Compute vendor KPIs (sales, margin, turnover, stuck inventory)  
4. **Visualization** → Build an executive-friendly Power BI dashboard  

---

## Project Structure

| File/Folder                         | Purpose                                                     |
| ----------------------------------- | ----------------------------------------------------------- |
| `ingest_db.ipynb`                   | Ingests CSVs into SQLite with logging & error handling      |
| `EDA.ipynb`                         | Data exploration, validation, and creation of summary table |
| `Vendor Performance Analysis.ipynb` | Vendor/brand-level KPI analysis                             |
| `inventory.db`                      | Final SQLite database                                       |
| `final_table.csv`                   | Clean dataset exported for Power BI                         |
| `Workflow.png`                      | Project flow diagram                                        |
| `Dashboard.jpg`                     | Dashboard preview (Power BI)                                |

---

## Dashboard Preview

<img width="1403" height="790" alt="Dashboard" src="https://github.com/user-attachments/assets/843ee841-089a-4624-821f-af85fa3d27b4" />

Key features:

* KPI Cards: Total Sales, Purchases, Gross Profit, Profit Margin  
* Top Vendors & Brands Leaderboard  
* Underperforming Vendors & Brands flagged  
* Scatter: **Sales vs. Profit Margin** (brand health check)  
* Inventory aging and stuck capital overview  

---

## Business Questions Answered

* Which vendors contribute most to revenue & profit?  
* Which vendors underperform and need reevaluation?  
* How much capital is stuck in unsold inventory?  
* What are the average margins by brand & vendor?  
* Do bulk purchases actually reduce unit cost?  
* Which brands require promotions or price adjustments?  

---

## Key Insights & Metrics

| Metric               | Value     |
| -------------------- | --------- |
| **Total Sales**      | \$441.41M |
| **Total Purchases**  | \$307.34M |
| **Gross Profit**     | \$134.07M |
| **Profit Margin**    | 38.72%    |
| **Unsold Inventory** | \$2.71M   |

Insights:

* Vendor sales & GP highly concentrated: top 10 vendors drive majority of profit  
* Several vendors (<1% contribution) consume resources but add little value  
* Brands with <15% margin flagged for promotion or renegotiation  
* \$2.7M locked in stuck inventory → clearance recommended  

---

## Methodology

1. **Data Sources**: Sales, Purchases, Inventory, Vendor Invoices  
2. **Ingestion**: Load into SQLite with logging & chunking for large files  
3. **Cleaning**: Handle missing values, unify formats, reconcile totals  
4. **Analysis**:  
   * Vendor Contribution = Sales & GP share  
   * Gross Margin % = (Revenue − COGS) / Revenue  
   * Inventory Turnover & DOH  
   * Bulk Purchase Elasticity (unit cost vs. quantity)  
5. **Visualization**: Power BI dashboard for executives  

---

## Tools & Skills Demonstrated

* **Python**: pandas, numpy, matplotlib, seaborn  
* **SQL**: Joins, aggregations, performance queries in SQLite  
* **Power BI**: Dashboarding, KPI cards, drill-through  
* **Statistics**: Confidence intervals, margin distributions, outlier detection  
* **Data Engineering**: Logging, error handling, reproducible pipeline  

---

## Low Performers Detected

* **Vendors (<1% Sales Contribution)**:  
  Dunn Wine Brokers, Circa Wines, Park Street Imports, Highland Wine Merchants, Alisa Carr Beverages  

* **Low-Margin Brands (<15%)**:  
  Flagged via **Sales vs. Profit Margin scatterplot**, segmented by `TargetBrand` classification  

---

## How to Run

1. Clone this repo  

   '''bash
   git clone https://github.com/username/Vendor-Performance-Analysis
   cd Vendor-Performance-Analysis
   
   pip install -r requirements.txt
   
2. Run Jupyter notebooks in order:
 - ingest_db.ipynb
 - EDA.ipynb
 - Vendor Performance Analysis.ipynb

3. Export final dataset: final_table.csv
4. Open Power BI → Connect to final_table.csv → Explore dashboard

