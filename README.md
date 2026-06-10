# zepto-SQL-data-analysis-project
# 📊 Zepto SQL E-commerce Data Analysis Project

SQL-based data analysis project built on a real-world e-commerce inventory dataset (Zepto). It includes database setup, data cleaning, exploratory data analysis, and business insights such as discounts, stock availability, revenue estimation, and product performance.

## 📌 Project Overview

The goal of this project is to simulate how data analysts in e-commerce and retail environments use SQL to analyze inventory data and generate actionable business insights.

This project covers:

✅ Database creation and setup

✅ Exploratory Data Analysis (EDA)

✅ Data cleaning and transformation

✅ Business-focused SQL analysis

✅ Revenue, pricing, inventory, and discount analysis

## 📁 Dataset Overview

The dataset represents an e-commerce inventory system where each row corresponds to a unique SKU (Stock Keeping Unit).

Duplicate product names may exist because products can appear in multiple package sizes, weights, discounts, or variations, reflecting real-world catalog structures.

### 🧾 Columns

* **sku_id** – Unique identifier for each product
* **name** – Product name
* **category** – Product category
* **mrp** – Maximum Retail Price
* **discountPercent** – Discount percentage
* **discountedSellingPrice** – Final selling price after discount
* **availableQuantity** – Available inventory quantity
* **weightInGms** – Product weight in grams
* **outOfStock** – Stock availability flag
* **quantity** – Units per package

## 🔧 Project Workflow

### 1. Database & Table Creation

```sql
DROP TABLE IF EXISTS zepto;

CREATE TABLE zepto(
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```

### 2. Data Import

The dataset was imported into PostgreSQL using pgAdmin.

Alternative import method:

```sql
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
```

### 3. 🔍 Data Exploration

* Record count analysis
* Null value checks
* Category analysis
* Stock availability analysis
* Duplicate SKU detection

### 4. 🧹 Data Cleaning

* Removed invalid price records
* Standardized price values
* Prepared data for analysis

### 5. 📊 Business Insights

* Best-value products by discount
* High-value products out of stock
* Revenue estimation by category
* Discount analysis
* Price-per-gram evaluation
* Product segmentation by weight
* Inventory distribution analysis

## 🛠️ Tools Used

* PostgreSQL
* SQL
* pgAdmin

## 🎯 Key Skills Demonstrated

* Database design
* Data cleaning
* Exploratory Data Analysis (EDA)
* SQL aggregations and filtering
* Business analytics
* Data-driven decision making

## 🚀 Project Goal

This project demonstrates practical SQL skills applied to a real-world e-commerce dataset, focusing on transforming raw inventory data into meaningful business insights.

