# E-Commerce Sales & Customer Analytics

An end-to-end analytics project using **SQL (Google BigQuery)** and **Power BI** to analyze e-commerce sales performance, customer behavior, product performance, payment methods, discounts, and business KPIs.

---

## 📌 Project Overview

This project analyzes a large e-commerce transaction dataset covering **2016–2018**.

The project follows an end-to-end analytics workflow:

**Raw Data → Data Cleaning → SQL Analysis → Business Insights → Power BI Dashboard**

The objective was to transform transactional data into actionable insights around sales performance, customer behavior, product/category performance, payment methods, and discount patterns.

---

## 🎯 Business Objectives

The analysis focuses on answering key business questions:

- How are sales and completed orders performing over time?
- Which product categories generate the highest GMV?
- Which SKUs contribute the most to completed GMV?
- What proportion of customers are repeat vs one-time customers?
- Which customers contribute the most GMV?
- How do payment methods perform?
- How are discounts distributed across categories?
- What is the monthly pattern of repeat customer behavior?
- How does order status distribution affect overall transaction activity?

---

## 🗂️ Dataset

**Dataset:** Pakistan's Largest E-Commerce Dataset (2016–2018)

The dataset contains transactional-level e-commerce records including:

- Order ID
- Customer ID
- SKU
- Product Category
- Price
- Quantity Ordered
- Grand Total
- Discount Amount
- Payment Method
- Order Status
- Order Date
- Customer Information

### Data Volume

- **584K+ transaction records**
- **408K+ unique orders**
- **115K+ unique customers**
- **84K+ unique SKUs**
- Date range: **July 2016 – August 2018**

---

## 🧹 Data Preparation

The raw CSV data was initially loaded into **Google BigQuery** as a raw table.

A cleaned analytical table was then created using SQL.

Key preparation steps included:

- Converting date fields into proper date types
- Converting numeric fields from text to numeric data types
- Handling `\N` values as NULL
- Standardizing column names
- Creating a calculated merchandise value
- Preserving the original source merchandise value for reference
- Validating row counts and key business identifiers

### Key Calculated Field

`Calculated MV = Price × Quantity Ordered`

Calculated merchandise value was used as the primary merchandise-value metric for the analysis.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Google BigQuery | Data storage, cleaning and SQL analysis |
| SQL | Data transformation and business analysis |
| Power BI | Interactive dashboard and visualization |
| DAX | Business measures and KPI calculations |
| Power Query | Data connectivity and preparation |
| GitHub | Project documentation and portfolio |

## 🔎 SQL Analysis

The SQL analysis covered multiple business areas:

1. **Monthly Sales Performance**  
   Analyzed completed orders, units sold, GMV, and average order value by month.

2. **Category Performance**  
   Compared categories based on completed orders, units sold, GMV, and average order value.

3. **Customer Behavior**  
   Classified customers into:
   - One-Time Customers
   - Repeat Customers

4. **Top Customers**  
   Identified the top customers based on completed GMV.

5. **Top SKUs**  
   Analyzed the highest-performing SKUs based on completed GMV.


## 📊 Power BI Dashboard

The Power BI dashboard contains three analytical pages.

### 1. Executive Sales Overview

Provides a high-level view of overall sales performance.

**KPIs**
- Completed GMV
- Completed Orders
- Units Sold
- Average Order Value

**Visuals**
- Monthly GMV Trend
- Monthly Completed Orders
- Order Status Overview

**Filters**
- Year
- Category
- Payment Method

### 2. Product & Category Performance

Focuses on product, category, discount, and payment-method performance.

**KPIs**
- Completed GMV
- Units Sold
- Discount Rate

**Visuals**
- Completed GMV by Category
- Discount Rate by Category
- Top 10 SKUs by Completed GMV
- Top 10 Payment Methods by Completed GMV

**Filter**
- Category

### 3. Customer Analytics

Analyzes customer composition, activity, repeat behavior, and customer contribution.

**KPIs**
- Total Customers
- Repeat Customers
- One-Time Customers

**Visuals**
- One-Time vs Repeat Customers
- Monthly Active Customers
- Top 10 Customers by Completed GMV
- Monthly Repeat Customer Rate

**Filter**
- Year

## 📌 Key Business Insights

### Customer Retention

The analysis identified:

- 67K completed customers
- 23K repeat customers
- 44K one-time customers
- Repeat customers represented approximately 34% of completed customers.

### Customer GMV Concentration

The top 10% of customers contributed approximately 69.5% of completed GMV, highlighting a strong concentration of GMV among higher-value customers.

### Category Performance

Mobiles & Tablets generated the highest completed GMV, followed by Appliances and Entertainment.

### Payment Methods

Payment methods showed significant differences in GMV and average order value, with several digital payment methods generating substantially higher AOV than Cash on Delivery.

### Discount Patterns

Discount rates varied considerably across categories, with some categories receiving significantly higher discount levels.

### Customer Behavior

The analysis demonstrates a meaningful difference between one-time and repeat customers and provides a monthly view of repeat-customer behavior to support customer-retention analysis.

## 🧮 Key Power BI Measures

Examples of DAX measures developed for the dashboard include:

**Completed GMV**

`Completed GMV = CALCULATE([Total GMV], ecommerce_clean[status] = "complete")`

**Completed Orders**

`Completed Orders = CALCULATE(DISTINCTCOUNT(ecommerce_clean[order_id]), ecommerce_clean[status] = "complete")`

**AOV**

`AOV = DIVIDE([Completed GMV], [Completed Orders])`

**One-Time Customers**

`One-Time Customers = [Total Customers] - [Repeat Customers]`

**Discount Rate**

`Discount Rate = DIVIDE([Total Discount], [Completed GMV])`

## 🗂️ Data Model

The Power BI model uses a transaction-focused analytical structure with a dedicated date dimension.

**Main Tables**
- `ecommerce_clean`
- `Dim_Date`

**Relationship**

`Dim_Date[Date]` → `ecommerce_clean[created_at]`

The date dimension supports time-based analysis across monthly and yearly visuals.

## 🎛️ Dashboard Features

The dashboard includes:

- Interactive slicers
- Cross-filtering
- Top N analysis
- KPI cards
- Monthly trend analysis
- Customer behavior analysis
- Reset Filters buttons
- Consistent dashboard formatting
- Separate analytical views for sales, products, and customers

## 📁 Repository Structure

- `screenshots/`
  - `01-executive-sales-overview.png`
  - `02-product-category-performance.png`
  - `03-customer-analytics.png`
- `E-Commerce Sales & Customer Analytics.pbix`
- `README.md`

## 💡 Project Outcome

This project demonstrates an end-to-end analytics workflow from raw transactional data through SQL-based data preparation and analysis to an interactive Power BI dashboard.

The project combines technical analytics skills with business-focused analysis across:

**Sales → Products → Customers → Payments → Discounts → Business Insights**

## 👤 Author

**Khurshid Ahmed**

Data Analyst | Supply Chain & Telecom Analytics

**Power BI | SQL | Tableau | SAP | Inventory Management**
