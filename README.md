# 🛒 Maven Market — Power BI Sales & Analytics Dashboard

## 📌 Project Overview
**Maven Market** is a multi-national grocery chain operating across **Canada, Mexico, and the United States**. 

The primary objective of this project is to build an interactive, decision-ready **Power BI Dashboard** that enables the sales and operations teams to monitor key business metrics—including **Revenue, Profit, Margins, and Return Rates**. The dashboard provides seamless cross-country comparisons, time-series trends, and detailed drill-downs at the product, customer, and store levels.

---

## 🎯 Key Performance Indicators (KPIs) & DAX Measures
The project centralizes all analytical calculations into a dedicated **Measures Table** using DAX:

* **Total Revenue:** Calculated using `SUMX()` over transaction sales.
* **Total Cost:** Derived by evaluating product cost against quantities sold.
* **Total Profit & Margin %:** 
  $$\text{Profit} = \text{Revenue} - \text{Cost}$$
  $$\text{Margin \%} = \text{DIVIDE}(\text{Profit}, \text{Revenue})$$
* **Transaction & Return Volume:** Total count of sales transactions vs. total product returns.
* **Return Rate %:** 
  $$\text{Return Rate \%} = \text{DIVIDE}(\text{Quantity Returned}, \text{Quantity Sold})$$

---

## 🏗 Data Architecture & Modeling
The data model follows a robust **Star Schema** with two Fact tables and conformed Dimension tables:

* **Fact Tables:** 
  * `FactSales` (Transactions)
  * `FactReturns` (Product Returns)
* **Dimension Tables:** 
  * `DimCalendar` (Date hierarchy: Year, Quarter, Month, Week)
  * `DimProducts` (Brand, Category, Cost, Retail Price)
  * `DimCustomers` (Demographics, Location)
  * `DimStores` & `DimRegions` (Store details linked to regional lookup tables for spatial analysis)

> **Relationships:** `1-to-Many` single-direction relationships built from dimensions to fact tables. Active relationships are established on standard date fields. Surrogate keys are hidden to maintain model clarity.

---

## 📊 Report Pages & Features

### 1. Executive Overview
* **KPI Cards:** Top-level metrics for Revenue, Profit, Margin %, and Return Rate %.
* **Sales Trends:** Monthly line charts showcasing revenue/profit seasonality, dips, and peaks.
* **Geographic Analysis:** Interactive map displaying store performance across the US, Mexico, and Canada.

### 2. Product Analysis
* **Category Breakdown:** Bar/Treemap visual highlighting revenue/profit by brand and category.
* **Profitability Matrix:** Detailed product-level drill-down for profit margins.
* **Return Hotspots:** Visual identification of products with elevated return rates.

### 3. Customer Insights
* **Top Performers:** Matrix ranking top customers by total revenue and profit contribution.
* **Segmentation:** Visual representation of customer purchasing behavior.

### 4. Returns & Operational Health
* **Return Rate Trends:** Monthly breakdown of returns.
* **Regional Risk Analysis:** Identifying high-return regions, stores, and product lines to mitigate inventory leakage.

---

## 💡 Key Business Insights
1. **Geographic Variance:** Highlights performance gaps across the US, Mexico, and Canada, enabling tailored regional marketing strategies.
2. **Seasonal Peaks:** Identifies core historical spikes in demand to optimize supply chain and store inventory management.
3. **Margin Control:** Pinpoints high-return items that drag down overall profitability despite high sales volumes.

---

## 🚀 How to Open & View
1. Download or clone this repository.
2. Open the `.pbix` file using **Power BI Desktop** (latest version recommended).
3. Ensure the underlying data sources/CSV links are updated if prompted.

---

## 🛠 Deliverables Included
* `Maven_Market_Report.pbix` — Fully built Power BI file.
* `Screenshots/` — Images of each dashboard page.
* `README.md` — Project documentation and setup guide.
