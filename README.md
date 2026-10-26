# Global Superstore — Business Intelligence Analysis with Power BI

## 1. Project Overview

This project uses Microsoft Power BI to analyze the Global Superstore dataset and develop an interactive business intelligence dashboard. The goal is to transform raw transactional data into actionable insights that support decisions related to sales performance, profitability, customers, products, and shipping operations.

The project covers data preparation, data modeling, DAX calculations, dashboard development, and business recommendations.

## 2. Business Objectives

The analysis aims to:

- Evaluate overall sales and profitability.
- Track performance across time periods.
- Compare sales and profit across regions, customer segments, and product categories.
- Identify products that contribute strongly to sales and products that may be reducing profitability.
- Examine customer purchasing patterns and shipping performance.
- Recommend actions that can improve business performance.

## 3. Tools and Technologies

- **Microsoft Power BI Desktop** — data modeling, DAX calculations, visualizations, and dashboard development.
- **Power Query** — data cleaning, transformation, and preparation.
- **DAX (Data Analysis Expressions)** — creation of business performance measures.
- **GitHub** — project documentation and portfolio presentation.

## 4. Dataset Description

The project uses the Global Superstore 2 dataset.

| Dataset characteristic | Initial finding |
|---|---|
| Total rows | 51,290 |
| Total columns | 24 |
| Date coverage | 2011–2014 |
| Distinct orders | 25,035 |
| Distinct customers | 1,590 |
| Exact duplicate rows | None identified |
| Missing postal codes | 41,296 |

The dataset contains order, customer, product, sales, profit, discount, shipping, and geographical information.

**Data-grain consideration:** The dataset contains transaction-level records. An order, customer, or product ID can legitimately appear across multiple rows, so repeated identifiers were not automatically treated as duplicate records.

## 5. Data Preparation

The following preparation steps were performed using Power Query:

1. Reviewed the dataset structure, columns, data types, and missing values.
2. Checked for exact duplicate records.
3. Converted order and shipping dates from text into date values using the appropriate locale.
4. Assigned suitable data types to numerical measures and identifiers.
5. Retained identifiers as text where appropriate and treated postal codes as text.
6. Reviewed discount values and retained their original decimal representation for percentage formatting.
7. Assessed missing postal codes and retained the records rather than removing a substantial portion of the dataset without justification.
8. Created a separate date table for time-based analysis and connected it to the main dataset using the order date.

## 6. Data Model and DAX Measures

The report includes a date table with year, month, month number, year-month, and quarter fields. The date table supports chronological analysis and time-based filtering.

The principal DAX measures are:

### Total Sales

```DAX
Total Sales = SUM('Global Superstore 2'[Sales])
```

### Total Profit

```DAX
Total Profit = SUM('Global Superstore 2'[Profit])
```

### Total Orders

```DAX
Total Orders = DISTINCTCOUNT('Global Superstore 2'[Order ID])
```

### Average Sales per Order

```DAX
Average Sales per Order =
DIVIDE([Total Sales], [Total Orders], 0)
```

### Profit Margin

```DAX
Profit Margin =
DIVIDE([Total Profit], [Total Sales], 0)
```

These measures provide a consistent basis for the report's KPI cards and visual analysis.

## 7. Dashboard Structure

### Page 1 — Executive Overview

Provides a high-level view of business performance through:

- Total Sales
- Total Profit
- Total Orders
- Average Sales per Order
- Profit Margin
- Monthly sales and profit trends
- Sales and profit by region
- Sales by customer segment

Interactive filters include year, region, segment, and category.

### Page 2 — Product and Category Performance

Examines performance at product and category level through:

- Sales by sub-category
- Profit by sub-category
- Sales by category
- Top 10 products by sales
- Bottom 10 products by profit

Interactive filters include year, category, and region.

### Page 3 — Customer and Operations

Explores customer purchasing patterns and shipping operations through:

- Top 10 customers by sales
- Sales by customer segment
- Shipping cost by ship mode
- Profit by ship mode
- Discount versus profit
- Customer and order detail table

Interactive filters include year, segment, and ship mode.

## 8. Initial KPI Results

The following figures were established during the initial analysis and KPI validation:

| KPI | Initial result |
|---|---:|
| Total Sales | 12,642,501.91 |
| Total Profit | 1,467,457.29 |
| Total Orders | 25,035 |
| Average Sales per Order | 504.99 |
| Profit Margin | 11.61% |

*Note: Values are presented in the dataset's original units. The currency has not been independently confirmed. Final published figures should be reconciled with the completed Power BI report.*

## 9. Preliminary Business Findings

The initial analysis suggests several areas for further investigation:

1. **Product category performance:** Technology recorded approximately 4.74 million in sales and 663,778.73 in profit. Other categories should be compared using both profit and margin.
2. **Customer segment contribution:** Consumer sales were approximately 6.51 million, followed by Corporate at 3.82 million and Home Office at 2.31 million. Sales contribution should be considered alongside profitability.
3. **Regional performance:** The Central region recorded approximately 2.82 million in sales and 311,403.98 in profit. Regional comparisons should also account for profit margin.
4. **Product profitability:** The bottom-10-products-by-profit visual can help identify products requiring pricing, cost, discount, or assortment reviews.
5. **Sales trends:** Monthly analysis can reveal peak and low-performing periods, helping inform planning and resource allocation.

These are preliminary findings. Product rankings, seasonal patterns, discount relationships, and shipping-mode comparisons should be confirmed directly against the final dashboard before being presented as definitive conclusions.

## 10. Risks and Opportunities

### Risks

- Products with persistently low or negative profit may weaken overall profitability.
- Heavy discounting may coincide with reduced profit margins and requires further investigation.
- Missing postal codes may limit some location-specific analyses.

### Opportunities

- Prioritize products and categories that demonstrate strong and sustainable profitability.
- Use customer and segment analysis to inform retention and engagement strategies.
- Compare shipping costs and profitability across shipping modes to identify opportunities for operational improvement.

## 11. Recommendations

1. Investigate products with negative or consistently low profit before making pricing or assortment decisions.
2. Establish evidence-based discount guidelines and monitor their relationship with profitability.
3. Prioritize regions and categories based on both profit contribution and margin.
4. Review shipping-mode costs alongside delivery requirements and business outcomes.
5. Introduce regular performance reviews using the dashboard to monitor KPIs, identify changes, and assign follow-up actions.

Recommendations should be refined after validating the detailed visual findings and considering relevant operational context.

## 12. Limitations

- The dataset covers 2011–2014 and may not represent current market conditions.
- The currency unit has not been independently confirmed.
- Missing postal codes limit some geographical analyses.
- Observed relationships, such as discount versus profit, do not by themselves establish causation.
- Preliminary category, segment, and regional figures should be reconciled with the final report before publication.

## 13. Project Deliverables

The intended project deliverables are:

- Power BI report file (`.pbix`)
- Dashboard export in PDF or image format
- Business Intelligence Overview Report
- Executive Summary
- Project README and documentation

Only include files in this list as completed deliverables once they have actually been saved and checked.

## 14. Conclusion

This project demonstrates an end-to-end business intelligence workflow, from data quality assessment and transformation to data modeling, KPI development, interactive reporting, and business recommendations.

The resulting dashboard is intended to help stakeholders explore performance from multiple perspectives and use evidence to guide decisions on sales, profitability, customers, products, and operations.