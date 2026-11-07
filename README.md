# Retail Fabric Lakehouse Analytics

## Enterprise Power BI & Microsoft Fabric Medallion Architecture Project

An enterprise-grade Microsoft Fabric, SQL Server, and Power BI analytics solution demonstrating Medallion Architecture (Bronze, Silver, Gold), Lakehouse Design, Star Schema Modeling, Advanced DAX, and Executive Dashboarding.

The project simulates a modern retail organization operating across global markets and GCC (UAE, Saudi Arabia, Qatar, Kuwait, Bahrain, and Oman), providing end-to-end visibility into sales performance, inventory movement, product performance, and operational KPIs.

---

# Executive Summary

This project demonstrates how to design and build a modern retail analytics platform using industry-standard data engineering and business intelligence best practices.

The solution follows a Medallion Architecture approach to transform raw retail transaction data into business-ready analytical datasets that support executive decision-making, operational monitoring, and performance management.

The final solution delivers:

- Retail Sales Analytics
- Product Performance Analysis
- Customer Insights
- Inventory Monitoring
- Executive KPI Reporting
- Regional Performance Analysis
- Multi-Currency Reporting
- Power BI Executive Dashboards

---

# Business Problem

Retail organizations often struggle with:

- Disconnected data sources
- Multiple reporting systems
- Delayed decision making
- Poor visibility into product performance
- Inventory management challenges
- Lack of executive dashboards
- Manual reporting processes

Business leaders require a centralized analytics platform that provides trusted, consistent, and actionable insights across all business functions.

---

# Business Objectives

The key objectives of this project are:

### Data Engineering

- Build an enterprise-grade Medallion Architecture
- Design scalable data pipelines
- Create governed analytical datasets
- Implement data quality standards

### Data Modeling

- Design a Star Schema model
- Build Fact and Dimension tables
- Optimize analytical performance
- Support self-service reporting

### Reporting & Analytics

- Create Executive Dashboards
- Develop KPI Monitoring Frameworks
- Build Interactive Power BI Reports
- Support strategic decision making

---

# Solution Architecture

```text
Retail Source Files
          │
          ▼
   Bronze Layer
   (Raw Data)
          │
          ▼
   Silver Layer
 (Cleansed Data)
          │
          ▼
    Gold Layer
 (Business Model)
          │
          ▼
  Semantic Model
          │
          ▼
 Power BI Reports
          │
          ▼
Executive Dashboard
```

---

# Medallion Architecture

## Bronze Layer

### Purpose

Raw data ingestion layer.

### Activities

- Source data loading
- Historical data preservation
- Initial validation
- Data landing zone

### Tables

```text
stg_RawSales
stg_RawProducts
stg_RawCustomers
stg_RawInventory
stg_RawStores
```

---

## Silver Layer

### Purpose

Data cleansing and transformation layer.

### Activities

- Data validation
- Duplicate removal
- Standardization
- Business rule implementation
- Data quality corrections

### Tables

```text
silver_Sales
silver_Products
silver_Customers
silver_Inventory
silver_Stores
```

---

## Gold Layer

### Purpose

Business-ready analytical layer.

### Activities

- Star Schema creation
- KPI preparation
- Reporting optimization
- Business aggregations

### Tables

```text
DimDate
DimProduct
DimCustomer
DimStore
DimRegion
DimCurrency

FactSales
FactInventory
FactReturns
```

---

# Technology Stack

| Layer | Technology |
|---------|------------|
| Source Data | CSV / Excel |
| Database | SQL Server |
| Data Processing | SQL |
| Data Warehouse | Lakehouse |
| Data Modeling | Star Schema |
| Reporting | Power BI |
| Version Control | GitHub |
| Architecture | Medallion Architecture |
| Documentation | Markdown |
| Diagramming | Draw.io |
| Future State | Microsoft Fabric |

---

# Data Sources

## Retail Transactions

Contains:

- Sales Transactions
- Order Information
- Customer Purchases
- Revenue Data

Sample Attributes:

```text
Transaction ID
Order Date
Customer ID
Product ID
Store ID
Sales Amount
Quantity
Discount
Profit
```

---

## Product Master

Contains:

- Product Details
- Product Categories
- Product Brands
- Product Pricing

Sample Attributes:

```text
Product ID
Product Name
Category
Subcategory
Brand
Unit Price
```

---

## Customer Data

Contains:

- Customer Information
- Region Details
- Demographics

Sample Attributes:

```text
Customer ID
Customer Name
Country
Region
Segment
```

---

# Data Warehouse Design

## Dimension Tables

### DimDate

Purpose:

Time Intelligence Analysis

Attributes:

- Date
- Month
- Quarter
- Year
- Fiscal Year

---

### DimProduct

Purpose:

Product Analytics

Attributes:

- Product Name
- Category
- Brand
- Product Type

---

### DimCustomer

Purpose:

Customer Analytics

Attributes:

- Customer Name
- Segment
- Region
- Country

---

### DimStore

Purpose:

Store Performance Analysis

Attributes:

- Store Name
- Location
- Region
- Country

---

### DimRegion

Purpose:

Regional Reporting

Attributes:

- Region
- Country
- GCC Indicator

---

### DimCurrency

Purpose:

Multi-Currency Reporting

Attributes:

- Currency Code
- Currency Name
- Exchange Rate

---

# Fact Tables

## FactSales

Measures:

- Revenue
- Quantity Sold
- Cost
- Profit

---

## FactInventory

Measures:

- Stock Quantity
- Inventory Value
- Stock Movement

---

## FactReturns

Measures:

- Return Quantity
- Return Value
- Return Percentage

---

# Key Performance Indicators (KPIs)

## Executive KPIs

- Total Revenue
- Total Profit
- Gross Margin %
- Revenue Growth %
- Profit Growth %

---

## Sales KPIs

- Revenue by Product
- Revenue by Region
- Revenue by Customer Segment
- Average Order Value

---

## Inventory KPIs

- Inventory Turnover
- Days Inventory Outstanding
- Stock Availability %
- Inventory Valuation

---

## Operational KPIs

- Store Performance
- Product Performance
- Return Rate %
- Sales Trend Analysis

---

# Dashboard Design

## Page 1: Executive Overview

Visuals:

- KPI Cards
- Revenue Trends
- Profit Trends
- Regional Performance
- Executive Summary

---

## Page 2: Sales Analytics

Visuals:

- Sales Trend Analysis
- Product Performance
- Category Analysis
- Top Customers
- Revenue Breakdown

---

## Page 3: Product Analytics

Visuals:

- Product Rankings
- Category Analysis
- Product Contribution %
- Product Trends

---

## Page 4: Inventory Analytics

Visuals:

- Inventory Health
- Stock Monitoring
- Inventory Turnover
- Inventory Valuation

---

## Page 5: Regional Analytics

Visuals:

- GCC Performance
- Global Sales Analysis
- Regional Contribution
- Geographic Analysis

---

# Example DAX Measures

```DAX
Total Revenue =
SUM(FactSales[SalesAmount])
```

```DAX
Total Profit =
SUM(FactSales[Profit])
```

```DAX
Profit Margin % =
DIVIDE([Total Profit],[Total Revenue])
```

```DAX
YTD Revenue =
TOTALYTD(
    [Total Revenue],
    DimDate[Date]
)
```

---

# Project Folder Structure

```text
retail-fabric-lakehouse
│
├── README.md
│
├── Data
│   ├── Raw
│   ├── Bronze
│   ├── Silver
│   └── Gold
│
├── SQL
│   ├── Staging
│   ├── Dimensions
│   ├── Facts
│   └── StoredProcedures
│
├── PowerBI
│
├── Documentation
│
├── Diagrams
│
├── Screenshots
│
└── Videos
```

---

# Project Roadmap

## Phase 1

- Repository Setup
- Documentation Setup
- Source Data Collection

## Phase 2

- SQL Environment Setup
- Data Import
- Data Profiling

## Phase 3

- Medallion Architecture Development
- Data Transformation
- Data Quality Validation

## Phase 4

- Star Schema Development
- Fact and Dimension Creation

## Phase 5

- Power BI Semantic Model
- Relationship Design
- DAX Development

## Phase 6

- Dashboard Development
- KPI Implementation
- UX Design

## Phase 7

- Microsoft Fabric Migration
- Direct Lake Implementation
- Lakehouse Architecture

---

# Screenshots

Project currently under development.

Screenshots will be added as each phase is completed.

---

# Lessons Learned

This section will be updated throughout the project lifecycle.

Topics include:

- Data Modeling
- SQL Optimization
- Star Schema Design
- DAX Optimization
- Power BI Performance Tuning
- Microsoft Fabric
- Medallion Architecture
- Lakehouse Design

---

# Future Enhancements

- Microsoft Fabric Lakehouse
- Direct Lake Semantic Model
- Incremental Refresh
- Row Level Security (RLS)
- Deployment Pipelines
- CI/CD Automation
- AI Insights
- Predictive Analytics
- Copilot Integration

---

# Author

**Rameez Shaikh**

Technical Lead | Power BI Developer | Data Analytics & Reporting Specialist | Microsoft Fabric Enthusiast

---

# Connect

GitHub: https://github.com/RameezShaikh05

LinkedIn: To Be Added

Portfolio Website: Coming Soon
