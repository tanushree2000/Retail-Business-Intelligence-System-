# 🌎 OptiRetail: Enhancing Retail with Data-Driven Insights

A complete cloud-based retail analytics solution using Microsoft Azure and Power BI. This project transforms raw customer order data into interactive dashboards, providing insights into customer behavior, product performance, and operational efficiency.

## 🎓 Project Overview

**Goal:** Build a predictive retail analytics dashboard that helps mid-sized retail companies improve customer retention, product planning, and inventory optimization.

**Tools Used:**
- Azure Data Factory (ETL Pipelines)
- Azure Blob Storage
- Azure SQL Database
- Power BI (Reporting and Dashboard)

---

## 🚀 Data Flow Architecture

1. **Raw Data Ingestion**: CSVs uploaded to Azure Blob Storage  
2. **Staging**: ADF pipelines load data into staging tables in Azure SQL  
3. **Transformation**: Stored procedures transform and load data into a Star Schema  
4. **Visualization**: Power BI connects to the SQL database to generate dashboards

<p align="center">
  <img src="Azure%20Cloud%20Data%20Ingestion%20Process.png" alt="Architecture Overview" width="700">
</p>

---

## 📊 Star Schema Model

- **Fact Table:** OrdersFact
- **Dimensions:**
  - CustomerDimension
  - ProductDimension
  - AisleDimension
  - DepartmentDimension
  - DayOfWeekDimension

<p align="center">
  <img src="Star%20Schema%20Model%20for%20OptiRetail.png" alt="Star Schema Model" width="700">
</p>

**Grain:** Each row in `OrdersFact` represents one product within a customer order.

---

## 📅 Key Business Problems Addressed

1. Low customer retention rates  
2. Lack of visibility into product performance  
3. Inefficient inventory and operations planning

---

## 🔢 Dataset Summary

From *Instacart Market Basket Analysis* (Kaggle):
- `orders.csv`
- `order_products__train.csv`
- `order_products__prior.csv`
- `products.csv`
- `departments.csv`
- `aisles.csv`

---

## 🔧 ETL Pipeline

<p align="center">
  <img src="Azure%20Cloud%20Data%20Ingestion%20Process.png" alt="Azure Cloud Data Ingestion" width="700">
</p>

- **LoadDataToStagingPipeline**: Loads CSVs into staging tables
- **LoadDataToWarehousePipeline**: Triggers stored procedures to load dimensions and fact tables
- **Stored Procedures:**
  - `LoadCustomerDimension`
  - `LoadProductDimension`
  - `LoadAisleDimension`
  - `LoadDepartmentDimension`
  - `LoadOrdersFact`

<p align="center">
  <img src="SQL%20Staging%20tables%20I.png" alt="SQL Staging Tables I" width="600">
  <br>
  <img src="SQL%20Staging%20tables%20II.png" alt="SQL Staging Tables II" width="600">
</p>

---

## 📊 Power BI Dashboards

### 1. Customer Behavior Insights
- Order distribution across week
- Customer lifecycle funnel
- Reorder patterns

### 2. Product & Sales Performance
- Top reordered products
- Sales by department and aisle
- Reorders by department

### 3. Department & Operational Efficiency
- Peak order/reorder days
- Department contribution to orders

### 4. Customer & Product Journey
- Customer segmentation (frequent, occasional, dormant)
- Lifetime value vs reorder frequency
- Drill-downs on customer-product pairs

---

## 🔄 Automation & Refresh

- Azure Data Factory pipelines run on schedule
- Power BI dashboards auto-refresh via Azure SQL connector

---

## 🚀 Key Outcomes

- 59% of orders were reorders, highlighting loyalty trends
- Sunday is peak day for both orders and reorders
- Produce and dairy departments drive most reorders
- High-value customers are frequent reordering buyers

---

## 📊 Impact

- Improved inventory & campaign planning
- Clearer customer segmentation for retention
- Faster reporting cycles with minimal manual work

---

For visuals, data flow diagrams, and dashboards: the report `OptiRetail Enhancing Retail with Insights.pdf`.

> Built with Microsoft Azure + Power BI 
