# zepto-SQL-data-analysis-project
SQL-based data analysis project built on a real-world e-commerce inventory dataset (Zepto). It includes database setup, data cleaning (price conversions), exploratory data analysis, and business insights such as discounts, stock availability, and product performance.

📌 Project Overview

The goal of this project is to simulate how data analysts in e-commerce or retail environments work with SQL to analyze real-world inventory data.

The project covers the full workflow from raw data handling to business insights, including data cleaning, exploratory analysis, and analytical SQL queries to support decision-making.

📁 Dataset Overview

The dataset is based on a real e-commerce inventory structure similar to Zepto’s product catalog. It represents a typical retail system where each row corresponds to a unique product SKU.

Duplicate product names exist because products may appear in different package sizes, weights, or variations, reflecting real-world catalog behavior.

🧾 Key Columns:
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
1. Database Setup
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

2. Data Import
Loaded CSV using pgAdmin's import feature.

If you're not able to use the import feature, write this code instead:

   \copy zepto(category,name,mrp,discountPercent,availableQuantity,
            discountedSellingPrice,weightInGms,outOfStock,quantity)
  FROM 'data/zepto_v2.csv' WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
Faced encoding issues (UTF-8 error), which were fixed by saving the CSV file using CSV UTF-8 format.

3. Data Exploration
Understanding dataset structure
Checking for missing or null values
Identifying product categories
Analyzing stock distribution
Detecting duplicate product entries
4. Data Cleaning
Removing invalid or zero price records
Converting price values from paise to rupees for standardization
5. Business Analysis
Identifying high-discount and value-for-money products
Detecting high-priced items that are out of stock
Estimating category-level revenue potential
Finding expensive products with low discounts
Analyzing average discount by category
Calculating price efficiency per gram
Segmenting products by weight categories (Low, Medium, Bulk)
Measuring total inventory weight per category
🛠️ Tools Used
PostgreSQL
SQL (DDL, DML, Aggregations, CASE logic)
pgAdmin / SQL CLI
🎯 Key Skills Demonstrated
Database design and schema creation
Data cleaning and transformation
Exploratory data analysis (EDA)
Business-oriented SQL thinking
Extracting insights from structured data
🚀 Project Goal

This project demonstrates practical SQL skills applied to a real-world e-commerce dataset, focusing on transforming raw data into meaningful business insights.
