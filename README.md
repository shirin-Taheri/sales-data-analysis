# Sales Data Analysis Using SQL

## Project Overview

This project explores a sales dataset using MySQL to analyse sales performance, order activity, product lines, and customer behaviour.

The goal is to extract meaningful business insights from relational data using SQL queries.

## Dataset

The dataset contains five related tables:

- `customers` — customer information
- `orders` — order dates and statuses
- `products` — product information and product lines
- `order_details` — products, quantities, and prices associated with orders
- `sales` — recorded sales values and deal sizes

The tables are connected using key relationships to analyse data across customers, orders, products, and sales.

## Key Business Questions

The analysis addresses questions including:

- What is the total recorded sales value?
- Which deal sizes and product lines generate the most sales?
- How does sales performance vary by year and month?
- Which customers place the most orders and generate the highest sales?
- How does sales performance differ across order statuses?
- What percentage of orders are shipped in each year?
- How does recorded sales value change across product lines over time?

## SQL Skills Demonstrated

- Aggregate functions: `SUM()`, `AVG()`, and `COUNT()`
- Grouping and filtering with `GROUP BY` and `HAVING`
- Joining multiple related tables
- Sorting and limiting results with `ORDER BY` and `LIMIT`
- Date functions for yearly and monthly analysis
- Common Table Expressions (CTEs)
- Window functions, including `LAG()`
- Calculating percentages and year-over-year changes

## Data Quality and Limitations

The source dataset contains discrepancies between the recorded `sales` values and values calculated as quantity multiplied by unit price.

For this project, the recorded `sales` column is used as the sales measure. The cause of these discrepancies has not been independently established, so results should be interpreted with this limitation in mind.

## Tools

- MySQL
- MySQL Workbench
- GitHub

## Project Structure

- `sales_analysis.sql` — SQL queries used to answer the business questions.

## Future Improvements

The next stage of this project is to develop an interactive Power BI dashboard to present key sales metrics and trends visually.
