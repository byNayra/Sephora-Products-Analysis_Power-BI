# Sephora Product Analysis Dashboard
## Project Documentation

## 1. Project Overview

This project uses Microsoft Power BI to analyze Sephora product-level data.

The goal is to explore product availability, discount distribution, and customer engagement through data preparation, DAX measures, and interactive visualizations.

The dashboard contains two pages:
- Overview
- Discount Analysis

## 2. Dataset Overview


Data Source: Kaggle
 The dataset was downloaded from Kaggle and used for this product-level analysis. It includes product details, pricing, customer engagement metrics, and availability indicator

The dataset contains product-level information, including:
- Product and brand details
- Product categories
- Original and sale prices
- Ratings and reviews
- Customer engagement (loves_count)
- Product availability
- Product attributes

The dataset does not include complete sales transactions or inventory quantities.

## 3. Data Preparation

### Missing Values Identified

Missing values were identified in fields including:
- rating
- reviews
- size
- variation_type
- price_usd
- sale_price_usd
- value_price_usd
- Product category and attribute fields
- Child product pricing fields

One record with a blank product_id was removed.

### Invalid Values Identified

- Two invalid values in rating: 27021 and 12795
- One invalid value in price_usd, where ingredient text appeared instead of a price
- Two text values in child_count, where numeric values were expected

### Data Transformation

- Reviewed missing and invalid values.
- Cleaned price_usd.
- Corrected data types.
- Formatted price fields as numeric values.
- Reviewed data conversion errors.
- Added an Index Column for product-level identification.

Missing values were not automatically treated as zero.

## 4. Business Questions

1. Where are out-of-stock products concentrated across categories and brands?
2. Which product types have higher Out-of-Stock Rates?
3. How are discounts distributed across categories and brands?
4. How can loves_count and ratings be used to explore customer engagement?
5. How might missing or invalid data affect product comparisons?

## 5. DAX Measures

### Total Products

```DAX
Total Products =
COUNTROWS('product_info')

Discounted Products =
COUNTROWS(
    FILTER(
        'product_info',
        NOT ISBLANK('product_info'[sale_price_usd]) &&
        NOT ISBLANK('product_info'[price_usd]) &&
        'product_info'[sale_price_usd] < 'product_info'[price_usd]
    )
)

Discount Rate =
DIVIDE(
    [Discounted Products],
    COUNTROWS('product_info')
)
Out-of-Stock Rate
Out of Stock Rate =
DIVIDE(
    SUM('product_info'[out_of_stock]),
    COUNT('product_info'[out_of_stock])
)

## 6. Analysis & Findings
6.1 Out-of-Stock Analysis

The analysis compares out-of-stock products across primary categories, brands, and product types.

Findings:

Makeup has the highest number of out-of-stock products among primary categories, with 213 products.

Sephora Collection has 60 out-of-stock products among the Top 10 brands analyzed, with an Out-of-Stock Rate of 17.09%.

Mini Size has the highest Out-of-Stock Rate at 10.80%.

Visuals:

Pie chart showing the distribution of out-of-stock products across primary categories.

Bar chart showing out-of-stock product counts by brand, using the Top 10 brands by out-of-stock count, with Out-of-Stock Rate in the tooltip.

Bar chart comparing Out-of-Stock Rates across product types/categories.

6.2 Discount Analysis

A product was counted as discounted when its sale price was lower than its original price, with both values available.

Findings:

269 products were identified as discounted.

The overall Discount Rate is 3.17%.

Makeup has the highest Discount Rate among primary categories at 6.11%, with 143 discounted products.

Sephora Collection has 78 discounted products and a 22.16% Discount Rate among the Top 20 brands by total product count.

Visuals:

Bar chart showing Discount Rate by primary category, with Discounted Products in the tooltip.

Bar chart showing Discounted Products by brand, using the Top 20 brands by total product count, with Discount Rate in the tooltip.

6.3 Customer Engagement

The dashboard includes loves_count as an indicator for exploring customer engagement at the product level.

Ratings and loves_count provide different perspectives on product feedback and engagement. The dashboard does not establish that one metric causes changes in the other.

## 7. Dashboard Structure
Page 1 — Overview

Provides a high-level view of the dataset and selected product metrics, with product availability and customer engagement visuals.

Page 2 — Discount Analysis

Focuses on discount-related metrics and comparisons across categories and brands.

## 8. Business Recommendations
Monitor Product Availability

Review out-of-stock patterns in Makeup, Sephora Collection, and Mini Size to identify products that may warrant further inventory investigation.

Review Discount Distribution

Examine discount patterns across categories and brands, particularly Makeup and Sephora Collection, and assess whether they align with business objectives.

Consider Multiple Engagement Indicators

Use ratings alongside loves_count when exploring customer engagement rather than relying on a single metric.

Improve Data Completeness

Review missing and invalid values in key fields and consider data validation checks for future datasets.

These recommendations indicate areas for further investigation; they do not establish causes or prove sales impact.

## 9. Limitations

The dataset contains product-level information rather than complete sales transaction data.

Inventory quantities and stock history are not available.

Missing values may affect the number of records included in certain calculations.

loves_count is an engagement indicator, not a direct sales measure.

Discount rates do not establish the impact of discounts on sales or profit.

Brand findings are limited to the stated Top 10 or Top 20 selections.

## 10. Conclusion

The dashboard provides an overview of product availability, discount distribution, and customer engagement across Sephora products. Further analysis using inventory, sales, and transaction data could help assess the business impact of these patterns and support more informed, data-driven decisions.

## 11. Tools & Technologies

Microsoft Power BI

Power Query

DAX

Microsoft Excel

## 12. Skills Demonstrated

Data Cleaning

Data Transformation

Data Quality Review

DAX Measure Development

KPI Analysis

Data Visualization

Business Analysis

Dashboard Design

Insight Documentation