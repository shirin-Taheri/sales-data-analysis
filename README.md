# Sales Data Analysis | MySQL & Power BI

## Project Overview

This project analyses a relational sales dataset using MySQL and Power BI to explore sales performance, customer behaviour, order activity, and monthly sales trends.

The project combines SQL-based analysis with interactive Power BI dashboards to transform sales data into meaningful business insights.

**Project objectives:**

- Analyse recorded sales and order performance.
- Identify leading customers and countries by sales.
- Explore customer distribution across countries.
- Monitor monthly sales trends and month-over-month growth.
- Identify and document data quality limitations.

## Dataset

The dataset contains five related tables:

- `customers` — customer information and geographic details.
- `orders` — order dates, statuses, and customer references.
- `products` — product information and product lines.
- `order_details` — product references, quantities, and unit prices.
- `sales` — recorded sales values and deal sizes.

The tables are linked using identifiers to support analysis across customers, orders, and sales. Some source-data relationships contain inconsistencies, as documented below.

## Tools & Technologies

- **MySQL** — querying and analysing relational data.
- **MySQL Workbench** — database management and SQL development.
- **Power BI Desktop** — data modelling, interactive dashboards, and visualisation.
- **DAX** — calculating sales measures, previous-month sales, and monthly growth.
- **GitHub** — project documentation and portfolio presentation.


## Dataset Source

The dataset used in this project was obtained from the [Sales DB Project GitHub Repository](https://github.com/asna208/sales-db-project).

The dataset consists of five CSV files: `customers`, `orders`, `order_details`, `products`, and `sales`.

These files were imported into MySQL for SQL analysis and used to develop the Power BI dashboards.

The source repository describes the data as derived from the Sample Sales Data dataset on Kaggle.

## SQL Analysis

The SQL analysis explores several business questions, including:

- What is the total recorded sales value?
- How does sales performance change across years and months?
- Which customers generate the highest sales?
- Which countries contribute the most sales?
- How do sales and orders differ across order statuses?
- How is recorded sales distributed across deal sizes?

### SQL Skills Demonstrated

- Aggregate functions: `SUM()`, `AVG()`, and `COUNT()`
- `GROUP BY` and `HAVING`
- `JOIN` operations across related tables
- `ORDER BY` and `LIMIT`
- Date functions and time-based analysis
- Common Table Expressions (CTEs)
- Window functions, including `LAG()`
- Percentage and growth calculations

The SQL queries are available in [`Sales_Analysis.sql`](Sales_Analysis.sql).

## Power BI Dashboards

Three report pages were developed to present the analysis visually.

### 1. Sales Overview Dashboard

Provides an overview of sales performance through:

- Total Sales
- Average Sale Value
- Sales Records
- Total Orders
- Total Customers
- Monthly Sales Trend
- Orders by Status
- Sales by Deal Size
- Interactive Month Slicer
![Sales Overview Dashboard](PowerBI/screenshots/Sales%20Overview%20Dashboard.png)

### 2. Customer Analysis Dashboard

Explores customer and geographic performance through:

- Countries by Customer Count
- Top 10 Customers by Sales
- Top 10 Countries by Sales
![Customer Analysis Dashboard](PowerBI/screenshots/Customer%20Analysis%20Dashboard.png)

### 3. Sales Performance Dashboard

Examines changes in sales performance over time through:

- Monthly Sales Trend
- Monthly Sales Performance and Growth Table
- Month-over-Month Sales Growth (%)

The report uses DAX measures to calculate previous-month sales and monthly sales growth.
![Sales Performance Dashboard](PowerBI/screenshots/Sales%20Performance%20Dashboard.png)


The Power BI report file is available here:

[Download Power BI Dashboard](PowerBI/Sales_Analysis_Dashboard.pbix)

## Key Findings

- **Total recorded sales:** 10,032,628.85.
- **Total orders:** 2,823.
- **Total customers in the customer table:** 91.
- **Highest annual recorded sales:** 2004, with 4,755,179.21.
- **Leading customer by recorded sales:** Euro Shopping Channel, with 912,294.11.
- **Leading country by recorded sales:** USA.
- Monthly sales exhibit substantial fluctuations, including pronounced peaks in November 2003 and November 2004.

These findings reflect the recorded sales values in the supplied dataset and should be interpreted alongside the data limitations below.

## Data Quality and Limitations

Several data quality issues were identified during the analysis.

### 1. Recorded Sales vs. Calculated Sales

The source dataset contains discrepancies between the recorded `sales` values and amounts calculated as quantity multiplied by unit price.

The analysis consistently uses the recorded `sales` column as its sales measure. The cause of these differences has not been independently established.

### 2. Product Reference Inconsistencies

The `products` table contains 109 product IDs, while `order_details` contains product ID references extending beyond that range.

Of the 2,823 order-detail records, 2,714 do not match a product ID in the `products` table.

These inconsistencies are present in the source data and prevent reliable product-line sales analysis across the complete dataset.

Product-line visualisations were therefore excluded from the final Power BI dashboards rather than assigning unsupported product classifications.

### 3. Missing Customer Reference

The `orders` table contains 27 orders referencing `Customer_id = 9`, but this ID does not exist in the `customers` table.

The recorded sales associated with these orders total 93,170.66.

These sales remain included in overall sales totals but cannot be reliably attributed to a named customer or country using the available customer data.
