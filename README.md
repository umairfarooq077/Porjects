# Sales-Analysis---SQL---PowerBI
Atliq Hardware facing declining sales, they need real-time sales data insights of all regions to make better decisions.
The purpose is to discover sales insights to sales team for decision support and end result will be a dashboard helping in data-driven decision making.
Feel Free to connect me over LinkedIn for such projects and insights : https://www.linkedin.com/in/umairfarooq077/

We got MySQL database from the company and ran some of the SQL queries to do our preliminary analysis. Then we performed ETL in the PowerBI for data visualization purpse. We created dashboard which included all the important KPIS namely, Revenue, Sales Treand, Top Customer by regions and Quantities sold.

I am attaching MySQL file and PowerBI file for your reference. I will also be typing SQL queries here for you to understand them.

Show total number of customers
SELECT COUNT(*) AS total_customers 
FROM customers;

Show transactions for Chennai market (market code for chennai is Mark001
SELECT * 
FROM transactions
where market_code = 'Mark001';

Show distrinct product codes that were sold in chennai
select distinct product_code AS products_chennai
from transactions
WHERE market_code = 'Mark001';

Show transactions where currency is US dollars
SELECT * 
FROM transactions
where currency = 'USD';

Show transactions in 2020 join by date table
select * 
FROM transactions 
JOIN date
ON transactions.order_date = date.date
where date.year = '2020';

Show total revenue in year 2020
select SUM(transactions.sales_amount ) AS revenue
FROM transactions 
JOIN date
ON transactions.order_date = date.date
where date.year = '2020';

Show total revenue in year 2020, January Month
select SUM(transactions.sales_amount ) AS jan_revenue
FROM transactions 
JOIN date
ON transactions.order_date = date.date
where date.year = '2020' AND date.month_name = 'January';

Show total revenue in year 2020 in Chennai
select SUM(transactions.sales_amount ) AS Chennai_2020_revenue
FROM transactions 
JOIN date
ON transactions.order_date = date.date
where date.year = '2020' AND transactions.market_code = 'Mark001';
