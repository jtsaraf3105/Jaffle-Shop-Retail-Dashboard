# Jaffle Retail Store – End-to-End Data Engineering Capstone

## Overview

Designed and implemented an end-to-end batch data pipeline on the Databricks Lakehouse Platform to transform fragmented retail CSV datasets into a structured, analytics-ready Delta Lake warehouse using Medallion Architecture (Bronze–Silver–Gold).

The solution centralizes raw operational data into a scalable, governed single source of truth for analytics and business intelligence.

---

## Architecture

### Medallion Design

### Bronze Layer (Raw Ingestion)

- Ingested 6 raw CSV datasets (`customers`, `orders`, `order_items`, `products`, `supplies`, `stores`)
- Stored data in Delta format with append-only strategy for auditability
- Preserved original source schema and raw data integrity

### Silver Layer (Data Processing & Validation)

- Implemented data cleansing (null handling, format standardization, trimming)
- Deduplicated records using business keys
- Applied validation checks for schema consistency and referential integrity
- Enriched datasets via structured joins

### Gold Layer (Analytics & Modeling)

- Designed optimized Star Schema warehouse
- Built Fact Tables:
  - `fact_sales`
  - `fact_inventory`
- Built Dimension Tables:
  - `dim_customers`
  - `dim_products`
  - `dim_stores`
  - `dim_date`
  - `dim_supplies`
- Implemented advanced metrics:
  - Daily Sales
  - Customer Lifetime Value (CLV)
  - RFM Segmentation

---

## Data Modeling

- Defined fact table grain at **order-item level** for accurate revenue aggregation
- Implemented surrogate keys for dimension tables
- Built aggregations for reporting efficiency
- Leveraged Delta Lake for ACID guarantees and schema enforcement

---

## Analytics & Insights

Built advanced SQL-based business insights including:

- Customer RFM segmentation using NTILE window functions
- Cohort retention analysis
- Product bundle analysis (frequently bought together)
- Seasonal revenue trend analysis
- Store performance benchmarking
- Profitability segmentation

Executed queries via Databricks Serverless SQL Warehouse for scalable analytics workloads.

---

## Technology Stack

- Databricks Lakehouse
- PySpark
- Delta Lake
- SQL
- Unity Catalog

---

## Key Engineering Learnings

- End-to-end Medallion pipeline design
- Delta Lake schema enforcement and transaction handling
- Star schema dimensional modeling
- Window functions and analytical SQL optimization
- Lakehouse-based analytics architecture
