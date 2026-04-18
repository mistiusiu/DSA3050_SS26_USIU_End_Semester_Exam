# Project Title

![USIU Logo](assets/usiu-logo.png)

**Misati Nyambane - XXXX45**

**DSA3050A Spring Semester 2026**

## Project Overview

This project focuses on the end-to-end business intelligence lifecycle, from data acquisition to analytical insight, of a global supply chain dataset. The primary goal is to evaluate delivery efficiency and financial health across different geographic markets, customer segments, and product lines. By utilizing a Star Schema data model and advanced DAX measures, the analysis uncovers specific operational gaps and highlights factors that correlate with late deliveries and profit leakage.

## Problem Statement

The shipping company faces challenges in maintaining consistent delivery speeds and maximizing profit margins across its diverse product categories and global territories. There is a critical need to identify the root causes of late deliveries and fraudulent transactions while determining which product segments are underperforming. The project aims to answer: _Which factors drive logistical delays, and how can the company pivot its strategy to ensure high-margin, timely operations?_

## Dataset Description

The selected raw dataset has 53 columns and 180,519 rows on the supply chain of a shipping company. This dataset examines the payment methods, shipping destinations, order date and time, shipping date and time, and the like. Moreover, it has both categorical and numerical variables with two dedicated date fields. One pertaining to the order date and another pertaining to the shipping date. This enables (10 – update number) dimension tables to be created. This dataset was obtained from Kaggle under a CC0 (Creative Commons 0) license and was originally retrieved from Mendley Data under the same license.

This raw dataset has the key columns of:

- **Type** – The payment method used. This could inform whether delivery speed could be correlated with the means an individual pays. Although, this is a highly unlikely correlation.

- **Days_for_shipping_real** – The actual time it took to ship the products

- **Days_for_shipping_scheduled** – The time slotted to ship the product.

- **Delivery_Status** – The status of the delivery derived in part from the amount of time it took to ship the product viz a viz how long it was supposed to take.

- **order_date_DateOrders** – The date and time that a product was ordered.

- **shipping_date_DateOrders** – The date and time that a product was dispatched for shipment.

- **Shipping_Mode** – The priority rank of a shipment. There might be a correlation between this priority and whether a shipment is early or late.

- **Order_Profit_Per_Order** – The amount of money made net for the shipment. This value can be negative indicating the the company made a loss. There might be a correlation between how much profit is made and how much priority a product is given in shipment.


## Tools Used

**Power BI Desktop:** For data modeling, DAX development, and visualization.

**Power Query (M):** For data cleaning, normalization, and ETL processes.

**GitHub:** For project documentation and version control.

**DAX (Data Analysis Expressions):** For advanced analytical measures and time intelligence.

## Steps Followed

1. **Data Acquisition:** Sourced the supply chain dataset from Mendeley Data/Kaggle.

2. **Data Cleaning:** Removed 24 irrelevant or sensitive columns (e.g., passwords, emails). Standardized casing, handled "FALSE" values as nulls, and corrected geographic abbreviations (e.g., EE. UU. to USA).

3. **Modeling:** Developed a Star Schema with a central FactSupplyChain table surrounded by 16 dimensions. Set up Role-Playing Dimensions for Order Date and Shipping Date.

4. **DAX Development:** Created 8+ measures (YTD Sales, Sales Growth %, Profit Margins) and 2 calculated columns for segmentation.

5. **Visualization:** Designed a 3-page interactive report consisting of an Executive Summary, Detailed Analysis (Drill-downs), and Performance Monitoring (KPIs).

6. **Insight Generation:** Performed cross-comparison analysis to identify fraudulent patterns and high-growth markets.

## Dashboard Features

**Executive Summary:** High-level KPIs and slicers for rapid situational awareness.

**Drill-Down Logic:** Ability to move from Category level down to specific Product performance.

**Sync Slicers:** Filters applied on the first page propagate throughout the entire report for a seamless user experience.

**Analytical Visuals:** Utilized a Decomposition Tree for profit breakdown and Key Influencers to identify drivers of fraudulent orders.

**Conditional Formatting:** A heatmap applied to Profit Margins to instantly flag loss-making regions.

## Key DAX Measures

**Total Sales:** Primary KPI tracking the overall scale of business.

**Total Profit:** Aggregates net profit to assess financial health.

**Profit Margin %:** Identifies the efficiency of regions in generating value.

**Sales LY:** Uses SAMEPERIODLASTYEAR to provide a baseline for historical comparison.

**Sales Growth %:** A trend indicator calculating percentage change vs. the previous cycle.

**Total Sales YTD:** Tracks performance against annual targets.

## Key Insights

**Fraud Detection:** Fraudulent orders are exclusively correlated with Bank Transfer payments and originate primarily from Cincinnati, Ewa Beach, and West Jordan.

**Profit Leakage:** The company experienced significant losses in the Basketball and Strength Training categories within the Consumer segment.

**Growth Opportunities:** Nigeria and Canada are the highest growth markets for exports, while Philadelphia, Detroit, and Las Vegas are the top emerging domestic cities.

**Strategic Pivot:** High-profit Bread and Butter categories were identified as Fishing, Cleats, and Camping & Hiking.

## Challenges Encountered

The selected dataset is **~100 MB** in size with more than 180,000 rows across 53 columns thus importing and manipulating the data often caused my device to run quite hot for extended periods of time. Additionally, implementing Time Intelligence required the creation of a dedicated Date Table to resolve duplicate value errors in the raw order date fields.

## Conclusion

The analysis successfully identifies the critical intersections between logistics and finance. By shifting focus away from loss-making sports categories and increasing scrutiny on specific payment methods in high-risk cities, the company can significantly protect its margins. Maintaining the current trajectory in high-growth regions like Canada and Nigeria will ensure long-term scalability and operational excellence.
