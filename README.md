# 📊 SQL Data Analytics Project

> Advanced SQL analytics project built on top of curated Gold Layer data models from a Medallion Data Warehouse.

This project focuses on transforming business-ready customer, product, and sales data into actionable insights using SQL Server.

The underlying data originates from ERP and CRM systems and has already been integrated, cleaned, and modeled through a separate Data Warehouse project. Leveraging the Gold Layer tables, this project applies exploratory analysis, KPI development, segmentation, ranking, trend analysis, cumulative calculations, and performance benchmarking to support data-driven business decisions.

The primary goal is to demonstrate how SQL can be used beyond data retrieval to perform comprehensive business analytics and reporting.

## 🏗️ Data Foundation

This analytics project is built on top of a separate Medallion Data Warehouse project.

Source Systems:
- ERP System
- CRM System

Warehouse Layers:
- Bronze Layer (Raw Data)
- Silver Layer (Cleaned & Transformed Data)
- Gold Layer (Business-Ready Data)

This repository focuses exclusively on analytics performed on the Gold Layer.

```text
ERP ─┐
     ├──► Data Warehouse Project
CRM ─┘

Bronze → Silver → Gold
                     │
                     ▼
          SQL Analytics Project
```
# 📂 Analytics Dataset

The analyses in this project are performed on three Gold Layer tables.

## gold.dim_customers

Contains customer demographic and profile information.

### Key Attributes

- customer_key
- customer_id
- first_name
- last_name
- country
- gender
- marital_status
- birthdate

---

## gold.dim_products

Contains product master data.

### Key Attributes

- product_key
- product_id
- product_name
- category
- subcategory
- cost
- product_line

---

## gold.fact_sales

Contains transactional sales records.

### Key Attributes

- order_number
- customer_key
- product_key
- order_date
- sales_amount
- quantity
- price

# 🎯 Analytical Areas

This project explores business performance across three domains:

### Customer Analytics

- Customer segmentation
- Customer value analysis
- Customer purchasing behavior
- Customer lifecycle metrics

### Product Analytics

- Product performance
- Product rankings
- Category contribution
- Product segmentation

### Sales Analytics

- Revenue analysis
- Trend analysis
- Running totals
- Performance benchmarking

Exploratory Analytics

1. Database Exploration
2. Dimension Exploration
3. Date Exploration
4. Measures Exploration

↓

Advanced Analytics

5. Magnitude Analysis
6. Ranking Analysis
7. Change Over Time Analysis
8. Cumulative Analysis
9. Performance Analysis
10. Data Segmentation
11. Part-to-Whole Analysis

↓

Business Reports

12. Customer Report
13. Product Report

# 🛠️ SQL Techniques Used

### Querying

- Joins
- Subqueries
- CTEs
- Views
- Aggregate Functions

### Window Functions

- RANK()
- ROW_NUMBER()
- SUM() OVER()
- AVG() OVER()

### Analytics

- KPI Development
- Trend Analysis
- Segmentation
- Performance Benchmarking
- Revenue Analysis

# 📁 Project Structure

```text
sql-data-analytics-project/
│
├── datasets/
│   │
│   ├── DataWarehouseAnalytics.bak
│   │
│   └── csv_files/
│       ├── gold.dim_customers.csv
│       ├── gold.dim_products.csv
│       ├── gold.fact_sales.csv
│       ├── gold.report_customers.csv
│       └── gold.report_products.csv
│
├── scripts/
│   ├── 00_init_database.sql
│   ├── 01_database_exploration.sql
│   ├── 02_dimensions_exploration.sql
│   ├── 03_date_range_exploration.sql
│   ├── 04_measures_exploration.sql
│   ├── 05_magnitude_analysis.sql
│   ├── 06_ranking_analysis.sql
│   ├── 07_change_over_time_analysis.sql
│   ├── 08_cumulative_analysis.sql
│   ├── 09_performance_analysis.sql
│   ├── 10_data_segmentation.sql
│   ├── 11_part_to_whole_analysis.sql
│   ├── 12_report_customers.sql
│   └── 13_report_products.sql
│
└── README.md
```

---

# ⚡ Setup

You can explore the project using either of the following approaches.

## Option A — Restore Database Backup (Recommended)

The fastest way to get started is by restoring the provided SQL Server backup.

### Steps

1. Open SQL Server Management Studio (SSMS).
2. Right-click **Databases** → **Restore Database**.
3. Select the backup file:

```text
datasets/DataWarehouseAnalytics.bak
```

4. Complete the restore process.
5. Execute the analytics scripts inside the `scripts` folder.

---

## Option B — Import CSV Files

If you prefer to build the analytical model manually, use the provided Gold Layer CSV files.

### Files

```text
datasets/csv_files/gold.dim_customers.csv
datasets/csv_files/gold.dim_products.csv
datasets/csv_files/gold.fact_sales.csv
```

### Steps

1. Create a new database in SQL Server.
2. Import the Gold Layer CSV files into SQL Server tables.
3. Execute the analytics scripts in numerical order.

---

## Output Reports

The repository also includes pre-generated analytical report outputs:

```text
datasets/csv_files/gold.report_customers.csv
datasets/csv_files/gold.report_products.csv
```

These files contain the final customer and product analytical views generated by:

```text
12_report_customers.sql
13_report_products.sql
```

and can be used for validation or further reporting.
