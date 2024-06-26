## Sales Analysis

## Problem Statement:-
You are a database administrator. You want to use the data to answer a few questions about your customers, especially about the sales and profit coming from different states, money spent in marketing and various other factors such as COGS (Cost of Goods Sold), budget profit etc. You plan on using these insights to help find out which items are being sold the most. You have been provided with the sample of the overall customer data due to privacy issues. But you hope that these samples are enough for you to write fully functioning SQL queries to help answer the questions.

## Dataset:-

The 3 key datasets for this case study:

- a. FactTable: The Fact Table has 14 columns mentioned below and 4200 rows. Date, ProductID, Profit, Sales, Margin, COGS, Total Expenses, Marketing, Inventory, Budget Profit, Budget COGS, Budget Margin, Budget
Sales, and Area Code Note: COGS stands for Cost of Goods Sold
- b. ProductTable: The ProductTable has four columns named Product Type, Product, ProductID, and Type. It has 13 rows which can be broken down into further details to retrieve the information mentioned in theFactTable. 
- c. LocationTable: Finally, the LocationTable has 156 rows and follows a similar approach to ProductTable. It has four columns named Area Code, State, Market, and Market Size.

  The dataset is available in " .csv " file check it out
  
## Tasks  performed:-
1. Display the number of states present in the LocationTable.
2. How many products are of regular type?
3. How much spending has been done on marketing of product ID 1?
4. What is the minimum sales of a product?
5. Display the max Cost of Good Sold (COGS).
6. Display the details of the product where product type is coffee.
7. Display the details where total expenses are greater than 40.
8. What is the average sales in area code 719?
9. Find out the total profit generated by Colorado state
10. Display the average inventory for each product ID.
11. Display state in a sequential order in a Location Table.
12. Display the average budget of the Product where the average budget margin should be greater than 100.
13. What is the total sales done on date 2010-01-01?
14. Display the average total expense of each product ID on an individual date.
15. Display the table with the following attributes such as date, productID, product_type, product, sales, profit, state, area_code.
16. Display the rank without any gap to show the sales wise rank.
17. Find the state wise profit and sales.
18. Find the state wise profit and sales along with the product name.
19. If there is an increase in sales of 5%, calculate the increasedsales.
20. Find the maximum profit along with the product ID and producttype.
21. Create a stored procedure to fetch the result according to the product type from Product Table.
22. Write a query by creating a condition in which if the total expenses is less than 60 then it is a profit or else loss. 
23. Give the total weekly sales value with the date and product ID details. Use roll-up to pull the data in hierarchical order.
24. Apply union and intersection operator on the tables which consist of attribute area code.
25. Create a user-defined function for the product table to fetch a particular product type based upon the user’s preference.
26. Change the product type from coffee to tea where product ID is 1 and undo it.
27. Display the date, product ID and sales where total expenses are between 100 to 200.
28. Delete the records in the Product Table for regular type.
29. Display the ASCII value of the fifth character from the columnProduct.

## Tools used:

- Excel:- For data cleaning
- MS SQL:- For Data analysis

  ## Data Analysis

 Display the average budget of the Product where the average budget margin should be greater than 100.
 ```sql 
select * from fact
select * from Product

SELECT p.ProductId,p.Product, AVG(f.Budget_Sales) AS AvgBudgetSales
FROM Fact f
JOIN Product p
ON f.ProductID = p.ProductID
GROUP BY p.Product, p.ProductId
HAVING AVG(f.Budget_Margin) > 100
order by AvgBudgetSales desc
```
Change the product type from coffee to tea where product ID is 1 and undo it.
```sql
select * from Product

-- Update the product type to 'tea':
UPDATE Product
SET Product_Type = 'tea'
WHERE ProductID = 1;

-- Verify the change:
SELECT ProductID, Product, Product_Type, Type
FROM Product
WHERE ProductID = 1;

-- Undo the change (rollback):
BEGIN TRANSACTION;
UPDATE Product
SET Product_Type = 'coffee'
WHERE ProductID = 1;
COMMIT TRANSACTION;

--Verify the rollback:
SELECT ProductID, Product,Product_Type, Type
FROM Product
WHERE ProductID = 1;
```

All the solution to the above query is uploaded in pdf format "SQL Case Study - 1 "

## Result: 

After solving all these questions, the results will include various insights and data points derived from the provided datasets. The realizations derived from these results may include:-

- Understanding Data Distribution: By counting the number of states present in the LocationTable, we gain insight into the geographical spread of the data.
- Product Analysis: Knowing the number of products that are of regular type helps in understanding the product portfolio.
- Marketing Spending: Calculating the spending on marketing for a specific product (Product ID 1) helps in assessing marketing strategies and effectiveness.
- Sales Analysis: Identifying the minimum and maximum sales figures provides insights into sales performance.
- Cost Analysis: Finding the maximum Cost of Goods Sold (COGS) helps in understanding cost structures and profitability.
- Product Type Filtering: Retrieving details of products with a specific type (coffee in this case) allows for targeted analysis of product categories.
- Expense Analysis: Filtering records based on total expenses being greater than a certain threshold helps in identifying high-expense transactions or areas.
- Regional Performance: Calculating the average sales in a specific area code (719 in this case) provides insights into regional performance and market potential.
- State-wise Profit: Determining the total profit generated by a specific state (Colorado in this case) helps in understanding regional profitability.

Each of these queries and their results contribute to a comprehensive analysis of the provided data, aiding decision-making processes such as resource allocation, marketing strategies, and product management.



THANK YOU 
