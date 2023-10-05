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

## Importing Data in Power BI using ODBC Connector
1. **Install MySQL ODBC Driver**:
   - Download and install the MySQL ODBC driver from the official MySQL website: [MySQL ODBC Downloads](https://dev.mysql.com/downloads/connector/odbc/).

2. **Create a DSN (Data Source Name)**:
   - Open the ODBC Data Source Administrator on your computer.
     - On Windows, you can typically find it in the Control Panel under Administrative Tools.
   - Navigate to the "System DSN" tab.
   - Click "Add" to create a new System DSN.
   - Select the MySQL ODBC driver you installed in step 1.
   - Configure the DSN settings, including the connection details to your MySQL database (hostname, port, username, password, etc.).
   - Test the connection to ensure it's working correctly.

3. **Open Power BI Desktop**:
   - Launch Power BI Desktop on your computer.

4. **Get Data**:
   - In Power BI Desktop, go to the "Home" tab in the ribbon.
   - Click on "Get Data."

5. **Select ODBC**:
   - In the "Get Data" window, search for "ODBC" and select "ODBC."

6. **Configure ODBC Connection**:
   - In the "ODBC" window, select the DSN you created in step 2 from the dropdown list.
   - Click "OK."

7. **Connect to Database**:
   - In the "Navigator" window that appears, choose the tables or views you want to import from your MySQL database.
   - You can also write custom SQL queries if needed.
   - Click "Load" to import the selected data into Power BI.

8. **Transform and Visualize Data**:
   - Once the data is loaded into Power BI, you can transform it, create relationships between tables, and build your reports and dashboards.

9. **Refresh Data**:
 -Set up a data refresh schedule to keep your Power BI reports up-to-date with the latest data from your MySQL database.
