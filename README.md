# zepto-SQL-data-analysis-project
SQL-based data analysis project built on a real-world e-commerce inventory dataset (Zepto). It includes database setup, data cleaning (price conversions), exploratory data analysis, and business insights such as discounts, stock availability, and product performance.

📌 Project Overview

The goal of this project is to simulate how data analysts in e-commerce or retail environments work with SQL to analyze real-world inventory data.

The project covers the full workflow from raw data handling to business insights, including data cleaning, exploratory analysis, and analytical SQL queries to support decision-making.

📁 Dataset Overview

The dataset is based on a real e-commerce inventory structure similar to Zepto’s product catalog. It represents a typical retail system where each row corresponds to a unique product SKU.

Duplicate product names exist because products may appear in different package sizes, weights, or variations, reflecting real-world catalog behavior.

🧾 Key Columns
sku_id: Unique identifier for each product entry
name: Product name
category: Product category (e.g., Snacks, Beverages, Fruits)
mrp: Maximum Retail Price (converted from paise to ₹)
discountPercent: Discount applied on MRP
discountedSellingPrice: Final selling price after discount
availableQuantity: Inventory quantity available
weightInGms: Product weight in grams
outOfStock: Stock availability status
quantity: Units per package
🔧 Project Workflow
Database Setup
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
Data Import
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
🔍 Data Exploration
Understanding dataset structure
Checking missing values
Identifying categories
Stock analysis
Duplicate product detection
🧹 Data Cleaning
Removing invalid/zero prices
Converting paise → rupees
📊 Business Insights
High discount products
Out-of-stock high MRP items
Revenue estimation per category
Price efficiency analysis
Weight segmentation (Low / Medium / Bulk)
Inventory weight per category
🛠️ Tools Used
PostgreSQL
SQL (DDL, DML, Aggregations, CASE)
pgAdmin / SQL CLI
🎯 Key Skills
Database design
Data cleaning
Exploratory data analysis
Business analytics using SQL
🚀 Project Goal

This project demonstrates practical SQL skills applied to a real-world e-commerce dataset, focusing on transforming raw data into meaningful business insights.
