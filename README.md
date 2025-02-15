## Sales Insights Data Analysis Project


. SQL database dump is in db_dump.sql file above. Download `db_dump.sql`

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`



![Sales Insights_page-0002](https://github.com/user-attachments/assets/f5f6ea61-5921-46dc-aedd-07d0caf8a9a4)


![Sales Insights_page-0003](https://github.com/user-attachments/assets/0bd7d3a3-80df-4c43-92f9-6bac2ea47864)

![Sales Insights_page-0004](https://github.com/user-attachments/assets/c877ccff-0be8-4842-a9d1-caa64d82284b)

view dashboard : https://app.powerbi.com/groups/me/reports/4f7015c1-3ba6-4247-96f5-7b837fce6f43/ReportSection?bookmarkGuid=1b527847-47ed-447f-85d8-64981e1b11af&bookmarkUsage=1&ctid=f00f2f39-2ff1-431f-aba9-3273f8ad190e&portalSessionId=2a7cc351-55ea-4476-8e64-de892996c9e5&fromEntryPoint=export
