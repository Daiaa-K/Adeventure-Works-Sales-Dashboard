# 📊 Sales Performance Dashboard (Excel)

## 📌 Overview
This project is an end-to-end **data analysis and dashboarding solution in Excel**, built using a star-schema data model, Power Pivot, and interactive dashboard techniques.

The dashboard provides insights into:
- Revenue, Profit, and Orders trends
- Customer and geographic performance
- Product-level metrics
- Time-based analysis (Year, Quarter, Month)

---

## 🧱 Project Workflow

### 1️⃣ Data Loading

Data was loaded into Excel using the **Data Model (Power Pivot)**.

#### Tables Used:
- `FactInternetSales` (fact table)
- `DimDate`
- `DimCustomer`
- `DimProduct`
- `DimGeography`
- `DimSalesTerritory`

#### Steps:
1. Import data into Excel (CSV / database)
2. Load into **Power Pivot Data Model**
3. Ensure each table has a primary key
4. Identify foreign keys in fact table

---

### 2️⃣ Data Cleaning & Preparation

Performed using **Power Query** and Excel transformations.

#### Key Cleaning Steps:
- Converted date fields to proper date format
- Handled missing/null values
- Standardized column names
- Removed duplicates
- Created derived columns:
  - Year
  - Month
  - Quarter
  - Day Name

---

### 3️⃣ Data Modeling (Star Schema)

A **star schema** was implemented for performance and clarity.

#### Structure:
- **Fact Table:** `FactInternetSales`
- **Dimension Tables:**
  - Date
  - Customer
  - Product
  - Geography
  - Sales Territory

#### Relationships:
- One-to-many relationships from dimensions → fact
- Connected using surrogate keys (e.g. `DateKey`, `ProductKey`)

#### Benefits:
- Faster calculations
- Cleaner aggregation
- Scalable design

---

### 4️⃣ Measures (DAX in Power Pivot)

Created a dedicated **Measures Table** for calculations.

#### Core Measures:
```DAX
#Orders = DISTINCTCOUNT(FactInternetSales[Sales Order Number])

Total Revenue = SUM(FactInternetSales[Sales Amount])

Total Profit = SUM(FactInternetSales[Profit])

Profit Margin = DIVIDE([Total Profit], [Total Revenue])

All Products = DISTINCTCOUNT(DimProduct[Product Key])

Sold Products = DISTINCTCOUNT(FactInternetSales[Product Key])