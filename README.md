# Sales Performance Dashboard (Excel)

## Overview
This project is an end-to-end data analysis and dashboard solution built in Microsoft Excel using Power Query, Power Pivot, and PivotTables. It follows a star schema data model and provides interactive insights into sales performance across time, geography, customers, and products.

The dashboard enables users to analyze key business metrics such as revenue, profit, order volume, and profit margins through dynamic visualizations and filters.

---

## Data Sources

The dataset consists of the following tables:

- FactInternetSales (fact table)
- DimDate
- DimCustomer
- DimProduct
- DimGeography
- DimSalesTerritory

---

## Data Loading

Data was imported into Excel and loaded into the Power Pivot Data Model.

Steps:
1. Import raw data files (CSV or database extract).
2. Load each table into Power Query.
3. Perform initial transformations if needed.
4. Load tables into the Data Model instead of worksheets.
5. Verify primary and foreign keys.

---

## Data Cleaning and Preparation

Data cleaning was performed using Power Query and Excel transformations.

Key steps:
- Converted date fields to proper date format
- Removed null or invalid records
- Standardized column names
- Removed duplicates
- Created derived columns:
  - Year
  - Month
  - Quarter
  - Day Name

---

## Data Modeling

A star schema was implemented to improve performance and maintain clarity.

Structure:
- Fact Table: FactInternetSales
- Dimension Tables:
  - DimDate
  - DimCustomer
  - DimProduct
  - DimGeography
  - DimSalesTerritory

Relationships:
- One-to-many relationships from dimension tables to the fact table
- Keys used:
  - DateKey
  - ProductKey
  - CustomerKey
  - GeographyKey
  - SalesTerritoryKey

---

## Measures (DAX)

Measures were created in Power Pivot using DAX.

Examples:
#Orders = DISTINCTCOUNT(FactInternetSales[Sales Order Number])

Total Revenue = SUM(FactInternetSales[Sales Amount])

Total Profit = SUM(FactInternetSales[Profit])

Profit Margin = DIVIDE([Total Profit], [Total Revenue])

All Products = DISTINCTCOUNT(DimProduct[Product Key])

Sold Products = DISTINCTCOUNT(FactInternetSales[Product Key])


---

## Analysis

The following analyses were implemented:

Time-based analysis:
- Yearly revenue and profit trends
- Monthly profit trend over time

Customer analysis:
- Profit distribution by gender

Geographical analysis:
- Performance by country and sales territory

Time segmentation:
- Weekday vs weekend performance
- Quarterly profit distribution

---

## Dashboard

An interactive dashboard was created in Excel with the following components:

- KPI cards:
  - Total Revenue
  - Total Profit
  - Profit Margin
  - Total Orders
  - Order Quantity

- Visualizations:
  - Line chart for trends
  - Bar chart for yearly comparison
  - Donut charts for distribution
  - Clustered bar chart for categorical comparison

- Filters:
  - Month slicer
  - Country slicer

---

## Interactivity

Metric switching:
- Implemented using Option Buttons (Form Controls)
- Linked to a selector cell
- SWITCH() function used to dynamically update values

Slicers:
- Connected to PivotTables for filtering by:
  - Month
  - Country

---

## Author

Diaa Kotb  
Data Analyst (Python, SQL, Excel)
