# InsightFlow Business Requirements

## 1. Business Objective

InsightFlow aims to analyze e-commerce performance across sales, customers, products, sellers, payments, and delivery operations.

The analysis focuses on identifying sales trends, customer behavior, product and seller performance, and delivery performance to support data-driven business decisions.

## 2. Business Questions

### Sales Performance
- How does revenue change over time?
- Which product categories generate the highest revenue?
- How does average order value change over time?

### Customer Performance
- How many unique customers place orders?
- What proportion of customers make repeat purchases?

### Product Performance
- Which product categories generate the highest sales?
- Which products have the highest number of units sold?

### Seller Performance
- Which sellers generate the highest revenue?
- How does seller performance vary across regions?

### Delivery Performance
- What percentage of orders are delivered late?
- Which states have the highest late delivery rate?
- How does delivery performance affect customer review scores?

### Payment and Satisfaction
- Which payment methods are most frequently used?
- What is the relationship between review scores and delivery performance?

## 3. KPI Definitions

| KPI | Definition | Calculation | Primary Grain |
|---|---|---|---|
| Total Orders | Number of unique orders | COUNT(DISTINCT order_id) | Order |
| Total Revenue | Total value of items sold | SUM(price) | Order Item |
| Total Customers | Number of unique customers | COUNT(DISTINCT customer_unique_id) | Customer |
| Average Order Value | Average revenue per order | Revenue / Orders | Order |
| Units Sold | Total number of items sold | COUNT(order_item_id) | Order Item |
| Average Review Score | Average customer review score | AVG(review_score) | Review |
| Late Delivery Rate | Percentage of delivered orders delivered after estimated date | Late Orders / Delivered Orders | Order |
| On-Time Delivery Rate | Percentage of delivered orders delivered on or before estimated date | On-Time Orders / Delivered Orders | Order |
| Cancellation Rate | Percentage of orders that were canceled | Canceled Orders / Total Orders | Order |
| Repeat Customer Rate | Percentage of customers with more than one order | Repeat Customers / Total Customers | Customer |

## 4. Analytical Metric Layer

| Metric Area | Metrics | Main Source |
|---|---|---|
| Sales | Revenue, Freight Value, Order Value, Orders | orders + order_items |
| Customer | Unique Customers, Repeat Customers | customers + orders |
| Product | Units Sold, Product Revenue, Category Revenue | order_items + products |
| Seller | Seller Revenue, Units Sold, Orders | order_items + sellers |
| Delivery | Late Rate, On-Time Rate, Delivery Time | orders |
| Payment | Payment Value, Payment Type, Installments | payments |
| Satisfaction | Review Score, Review Distribution | reviews |

## 5. KPI Priority

| KPI | Priority | Dashboard |
|---|---|---|
| Total Revenue | Core | Executive Overview |
| Total Orders | Core | Executive Overview |
| Total Customers | Core | Executive Overview |
| Average Order Value | Core | Executive Overview |
| Late Delivery Rate | Core | Executive Overview |
| Average Review Score | Core | Executive Overview |
| Repeat Customer Rate | Secondary | Customer Insights |
| Units Sold | Secondary | Product Performance |
| Seller Revenue | Secondary | Seller Performance |
| Payment Value | Secondary | Payment Analysis |

## 6. Business Question to KPI Mapping

| Business Question | KPI / Metric |
|---|---|
| How does revenue change over time? | Total Revenue |
| Which categories generate the highest revenue? | Category Revenue |
| How many customers place orders? | Total Customers |
| How many customers return? | Repeat Customer Rate |
| Which products sell the most? | Units Sold |
| Which sellers generate the most revenue? | Seller Revenue |
| How well are orders delivered? | On-Time Delivery Rate |
| How many orders are late? | Late Delivery Rate |
| Which payment methods are most used? | Payment Count / Payment Value |
| How satisfied are customers? | Average Review Score |
| Does delivery performance affect satisfaction? | Late Delivery Rate + Average Review Score |