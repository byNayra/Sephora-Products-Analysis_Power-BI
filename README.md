# Sephora Product Analysis Dashboard | Power BI

## Project Overview

An interactive Power BI dashboard built to explore Sephora product data, focusing on product availability, discount distribution, and customer engagement.

The project involved data cleaning, transformation, DAX measure development, and business-focused visual analysis.

## Business Objectives

- Analyze out-of-stock products across categories and brands.
- Identify product types with higher Out-of-Stock Rates.
- Explore discount distribution across categories and brands.
- Explore customer engagement using loves_count and ratings.
- Review data quality issues that may affect analysis.

## Dashboard Pages

### 1. Overview
Provides an overview of product data, key metrics, product availability, and customer engagement.

### 2. Discount Analysis
Focuses on discount distribution across primary categories and brands.

## Key Findings

### Out-of-Stock Analysis
- Makeup has the highest number of out-of-stock products among primary categories, with 213 products.
- Sephora Collection has 60 out-of-stock products among the Top 10 brands analyzed, with an Out-of-Stock Rate of 17.09%.
- Mini Size has the highest Out-of-Stock Rate at 10.80%.

### Discount Analysis
- 269 products were identified as discounted.
- The overall Discount Rate is 3.17%.
- Makeup has the highest Discount Rate among primary categories at 6.11%, with 143 discounted products.
- Sephora Collection has 78 discounted products and a 22.16% Discount Rate among the Top 20 brands by total product count.

## Data Preparation

- Removed one record with a blank product_id.
- Reviewed missing and invalid values.
- Cleaned price_usd and corrected data types.
- Reviewed data conversion errors.
- Added an Index Column for product-level identification.

## Tools & Skills

- Power BI
- Power Query
- DAX
- Excel
- Data Cleaning & Transformation
- KPI Development
- Data Visualization
- Business Analysis
- Insight Documentation

## Analysis Process & Insight Log

An Insight Log was maintained throughout the project to document data quality observations, analysis steps, and findings.

See the Screenshots folder for dashboard pages and the Insight Log.

## Conclusion

The dashboard provides an overview of product availability, discount distribution, and customer engagement across Sephora products. Further analysis using inventory, sales, and transaction data could help assess the business impact of these patterns and support more informed, data-driven decisions.
