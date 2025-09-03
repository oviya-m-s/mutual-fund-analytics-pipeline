##  Project Overview

This project is an **ETL pipeline and analytics system** for **Mutual Fund NAVs (Net Asset Values)** with **benchmark comparisons**, inspired by Moneycontrol-style dashboards.  
It automates **data ingestion, transformation, storage, and analytics** using **Snowflake** and **Apache Airflow**, with visualization in **Power BI**.

---

## Data Extraction
- Scrapes **daily NAV data** directly from [AMFI India](https://www.amfiindia.com).
- Fetches **benchmark index values** (e.g., NIFTY 50, BSE Sensex) from external APIs.

---

## Data Storage (Snowflake)
- **`current_nav`** → Latest NAV values.  
- **`nav_history`** → Historical NAV tracking.  
- **`mutual_fund_company`** & **`mutual_fund_scheme`** → Fund houses and their schemes.  
- **`benchmark_index`** & **`benchmark_history`** → Benchmarks and their historical values.  
- **`scheme_benchmark_mapping`** → Links schemes to benchmarks.  
- **`etl_audit`** → Tracks ETL runs.  

---

## ⚙ETL Orchestration (Apache Airflow)
- Automated **DAG** scheduled to run daily at **6:00 AM**.
- Extracts NAV data → Loads into `current_nav` → Updates `nav_history`.  
- Updates benchmark data daily.  
- Runs **fund vs. benchmark comparison queries**.  
- Logs ETL run details into **`etl_audit`**.  

---

## Analytics
- Real-time **fund vs. benchmark performance comparison**.  
- **Historical performance tracking**.  
- Foundation for **return calculations, tracking error, and insights**.  

---
- Add **rolling returns, volatility, and risk-adjusted metrics**.  
- Expand Power BI dashboard for **interactive fund vs. benchmark analysis**.
