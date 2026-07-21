# Retail Sales Analytics using Microsoft Fabric

## Overview

An end-to-end retail analytics solution built using **Microsoft Fabric, PySpark, Delta Lake, and Power BI** following the **Medallion Architecture (Bronze-Silver-Gold)**.

This project demonstrates data ingestion, data transformation, dimensional modelling, semantic modelling, and interactive business intelligence reporting.

---

# Architecture

The project follows a modern end-to-end data engineering workflow using Microsoft Fabric Medallion Architecture with automated pipeline orchestration.

![Architecture Diagram](architecture/architecture_diagram.png)


---

# Technology Stack

- Microsoft Fabric
- Fabric Lakehouse
- PySpark
- Delta Lake
- SQL
- Power BI
- DAX
- Medallion Architecture


---

# Data Pipeline

## Bronze Layer

Raw data ingestion layer.

Activities:

- Loaded retail transaction CSV files into Microsoft Fabric Lakehouse
- Stored raw data in Delta format
- Maintained original source structure


---

## Silver Layer

Data cleaning and transformation layer.

Transformations:

- Removed invalid records
- Handled missing values
- Data type corrections
- Added Revenue calculation
- Added ingestion timestamp
- Performed data quality checks

---

# Data Pipeline Orchestration

Implemented an automated data pipeline using **Microsoft Fabric Data Factory** to orchestrate the complete data flow.

Pipeline Workflow:

Bronze Notebook  
↓  
Silver Notebook  
↓  
Gold Notebook  


Pipeline Features:

- Automated execution of Bronze, Silver, and Gold layer transformations
- Notebook dependency management
- Sequential execution workflow
- Centralized orchestration using Microsoft Fabric Pipeline
- Ready for scheduled refresh and production deployment


Pipeline Architecture:

![Fabric Pipeline](architecture/fabric_pipeline.png)

---

## Gold Layer

Business-ready analytical layer.

Implemented a Star Schema consisting of:

### Dimension Tables

### dim_customer

Contains:

- CustomerKey
- CustomerID
- Country
- Customer Revenue
- Customer Order Count
- Customer Segment


Customer Segmentation:

- VIP Customer
- Regular Customer
- Low Value Customer


---

### dim_product

Contains:

- ProductKey
- StockCode
- Description
- Product Revenue
- Quantity Sold
- Product Performance


Product Classification:

- High Performer
- Medium Performer
- Low Performer


---

### dim_date

Contains:

- DateKey
- Date
- Year
- Month
- Month Name
- Quarter
- Month Year
- Week Number
- Weekend Flag


---

### Fact Table

### fact_sales

Contains:

- Invoice Number
- Product Key
- Customer Key
- Date Key
- Quantity
- Unit Price
- Revenue
- Sales Category
- Quantity Category
- Return Flag


---

# Data Model

Implemented Star Schema:

             dim_customer
                  |
                  |
dim_date ---- fact_sales ---- dim_product



---

# Power BI Dashboard

Built an interactive retail analytics dashboard with three pages.

---

## Overview Dashboard

![Overview Dashboard](dashboard/screenshots/Overview.png)


Key Metrics:

- Total Revenue
- Total Orders
- Total Customers
- Total Quantity
- Average Order Value


Visuals:

- Revenue Trend Analysis
- Top 10 Products by Revenue
- Revenue Contribution by Country
- Country-wise Sales Analysis


---

## Customer Analytics Dashboard

![Customer Analytics Dashboard](dashboard/screenshots/Customer_Analytics.png)


Key Metrics:

- Total Customers
- VIP Customers
- Average Customer Revenue
- Average Orders per Customer


Visuals:

- Revenue Contribution by Customer Segment
- Top Customers by Revenue
- Customer Distribution by Country
- Customer Detail Analysis


---

## Product Analytics Dashboard

![Product Analytics Dashboard](dashboard/screenshots/Product_Analytics.png)


Key Metrics:

- Total Products
- Total Revenue
- Total Quantity Sold
- Average Product Revenue
- Top Product


Visuals:

- Top 10 Products by Revenue
- Product Performance Analysis
- Top Products by Quantity Sold
- Product Details Table


---

# Business Insights

Key insights generated:

- United Kingdom contributes the majority of revenue.
- VIP customers generate the highest revenue contribution.
- A small number of products contribute significantly to overall sales.
- Product performance segmentation identifies high-value products.
- Customer analytics helps understand purchasing behaviour.


---

# Project Workflow


CSV Files

↓

Microsoft Fabric Lakehouse

↓

Bronze Layer Notebook

↓

Silver Layer Notebook

↓

Gold Layer Notebook

↓

Fabric Data Pipeline Orchestration

↓

Semantic Model

↓

Power BI Dashboard

---

# Future Enhancements

- Schedule automated pipeline refresh
- Add product category classification
- Implement RFM customer segmentation
- Add sales forecasting using Machine Learning
- Implement real-time streaming analytics using Microsoft Fabric Real-Time Intelligence


---

# Repository Structure

Retail-Sales-Analytics-Microsoft-Fabric/

│
├── architecture/
│ ├── architecture_diagram.png
│ └── fabric_pipeline.png
│
├── dashboard/
│ └── screenshots/
│ ├── Overview.png
│ ├── Customer_Analytics.png
│ └── Product_Analytics.png
│
├── notebooks/
│ ├── Bronze_Notebook
│ ├── Silver_Notebook
│ └── Gold_Notebook
│
├── README.md
└── LICENSE

---

# Author

**Riya Mota**

Computer Science (AI & ML) Graduate

Skills:

Python | SQL | Power BI | Microsoft Fabric | PySpark | Data Analytics | Generative AI
