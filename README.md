# 🌎 OptiRetail: Enhancing Retail with Data-Driven Insights

A complete cloud-based retail analytics solution using Microsoft Azure and Power BI. This project transforms raw customer order data into interactive dashboards, providing insights into customer behavior, product performance, and operational efficiency.

## 🎓 Project Overview

**Goal:** Build a predictive retail analytics dashboard that helps mid-sized retail companies improve customer retention, product planning, and inventory optimization.

**Tools Used:**
- Azure Data Factory (ETL Pipelines)
- Azure Blob Storage
- Azure SQL Database
- Power BI (Reporting and Dashboard)

## 🚀 Data Flow Architecture

1. **Raw Data Ingestion**  
   CSVs uploaded to Azure Blob Storage.

2. **Staging**  
   ADF pipelines load data into staging tables in Azure SQL.

3. **Transformation**  
   Stored procedures transform and load data into a Star Schema.

4. **Visualization**  
   Power BI connects to the SQL database to generate dashboards.

![Architecture Overview](docs/Architecture_Overview_of_Data_Flow_Process.png)

## 📊 Star Schema Model

- **Fact Table:** OrdersFact
- **Dimensions:**
  - CustomerDimension
  - ProductDimension
  - AisleDimension
  - DepartmentDimension
  - DayOfWeekDimension

![Star Schema Model](docs/Star_Schema_Model_for_OptiRetail.png)

### Grain:
Each row in `OrdersFact` represents one product within a customer order.

## 📅 Key Business Problems Addressed

1. Low customer retention rates
2. Lack of visibility into product performance
3. Inefficient inventory and operations planning

## 🔢 Dataset Summary

From [Instacart Market Basket Analysis - Kaggle]:
- `orders.csv`
- `order_products__train.csv`
- `order_products__prior.csv`
- `products.csv`
- `departments.csv`
- `aisles.csv`

## 🔧 ETL Pipeline

- **LoadDataToStagingPipeline**: Loads CSVs into staging tables
- **LoadDataToWarehousePipeline**: Triggers stored procedures to load dimensions and fact tables
- **Stored Procedures:**
  - `LoadCustomerDimension`
  - `LoadProductDimension`
  - `LoadAisleDimension`
  - `LoadDepartmentDimension`
  - `LoadOrdersFact`

![SQL Staging Tables I](docs/SQL_Staging_Tables_I.png)
![SQL Staging Tables II](docs/SQL_Staging_Tables_II.png)

## 📊 Power BI Dashboards

### 1. Customer Behavior Insights
- Order distribution across week
- Customer lifecycle funnel
- Reorder patterns

![Customer Behavior Dashboard](docs/Customer_Behavior_Insights.png)

### 2. Product & Sales Performance
- Top reordered products
- Sales by department and aisle
- Reorders by department

![Product Performance Dashboard](docs/Product_and_Sales_Performance.png)

### 3. Department & Operational Efficiency
- Peak order/reorder days
- Department contribution to orders

![Operational Dashboard](docs/Department_and_Day_Insights.png)

### 4. Customer & Product Journey
- Customer segmentation (frequent, occasional, dormant)
- Lifetime value vs reorder frequency
- Drill-downs on customer-product pairs

![Customer Journey](docs/Customer_and_Product_Journey.png)

## 🔄 Automation & Refresh
- Azure Data Factory pipelines run on schedule
- Power BI dashboards auto-refresh via Azure SQL connector

## 🚀 Key Outcomes

- 59% of orders were reorders, highlighting loyalty trends
- Sunday is peak day for both orders and reorders
- Produce and dairy departments drive most reorders
- High-value customers are frequent reordering buyers

## 📊 Impact
- Improved inventory & campaign planning
- Clearer customer segmentation for retention
- Faster reporting cycles with minimal manual work

---

For visuals, data flow diagrams, and dashboards: check the `docs/` folder or the report `OptiRetail Enhancing Retail with Insights.pdf`.

> Built with Microsoft Azure + Power BI | IS 525 Final Project | Fall 2024
