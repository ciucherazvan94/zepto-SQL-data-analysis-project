# zepto-SQL-data-analysis-project
# 📊 Zepto SQL E-commerce Data Analysis Project

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

