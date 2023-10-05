# Sales_Insight
----------------

## Introduction
The Sales Insight project is a data visualization and analysis tool created using Power BI and MySQL. It aims to provide valuable insights into sales data, helping businesses make data-driven decisions and optimize their sales strategies.

Sales data is a valuable resource for any organization, and this project simplifies the process of extracting, storing, and visualizing this data. By using Power BI for visualization and MySQL for data storage, users can easily analyze historical sales performance, identify trends, and make informed decisions to improve sales strategies.

## Data Analysis Using SQL
1.Show all customer records
SELECT * FROM customers;

2.Show total number of customers
SELECT count(*) FROM customers;

3.Show transactions for Chennai market (market code for chennai is Mark001
SELECT * FROM transactions where market_code='Mark001';

4.Show distrinct product codes that were sold in chennai
SELECT distinct product_code FROM transactions where market_code='Mark001';

5.Show transactions where currency is US dollars
SELECT * from transactions where currency="USD"

6.Show transactions in 2020 join by date table
SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

7.Show total revenue in year 2020,
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

8.Show total revenue in year 2020, January Month,
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

9.Show total revenue in year 2020 in Chennai
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";


