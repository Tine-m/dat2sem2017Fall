# SQL EXERCISES

**Based on the [ClassicModels database](DatabaseClassicModels.sql).**

- 1 - Get the script file: DatabaseClassicModels.sql from the github repo
- 2 - Run the script on you local Mysql server
- 3 - Check that there were no errors and that 9 tables were created and filled with data.

###  SELECT (ONE TABLE only)

- 4 - Find all the French customers
- 5 - Find first name and last name on employees with the title ”sales rep”
- 6 - Find name and description of the motorcycle models that cost between 50$ and 100$
- 7 - Find the customer numbers for the orders that have been cancelled
- 8 - Find product lines and vendor for products with size 1:18

### ORDER BY
- 9 - List all the motorcycles sorted by product name
- 10 - List models with less than 1000 in stock sorted by quantity in stock with highest quantity at the top of the list
- 11 - List the Norwegian customers’ customer name and contact person sorted by the contact person’s first name

### FUNCTIONS
- 12 - How many German customers are there?
- 13 - What is the average price for classic car models?
- 14 - What is the price of the most expensive model from 'Autoart Studio Design’?
- 15 - How many different countries do the customers come from?
- 16 - What is the quantity in stock for 1:12 models?
- 17 - What is the highest profit amongst the products?

### GROUP BY
- 18 - What is the average price for each product line?
- 19 - How many different products does each vendor have?
- 20 - What is the profit percentage wise based on product scale?
- 21 - How many orders exist for each order status type?
- 22 - How many orders do each customer have?

### SELECT (MANY TABLES)
- 23 - Find all customer names and the name of the employee responsible for the customer
- 24 - Find all customer names and the name of the employee responsible for the customer for italian customers
- 25 - Find all customer countries and the names of the employees responsible for customers in the countries

### UPDATE
- 26 - Update Leslie Jenning’s last name to “Smith”
- 27 - Update Roland Keitel’s first name to “Dr. Roland”
- 28 - Update all spanish customers to be associated with employee Martin Gerard
- 29 - Update all motorcycles’ MSRP with extra 10%
- 30 - Update all customers with null in address Line2 to an empty string

### INSERT
- 31 - Insert a new product called bike and with some description
- 32 - Insert a new office for Copenhagen
- 33 - Insert two new products called mountainbike and triathlonbike at the same time

### DELETE
- 34 - Delete all payments older than '2003‐06‐18'
- 35 - Delete all customers with customer numbers lower than 150

### JOIN
- 36 - List all orders with order number, customer name and order date
- 37 - List all customers with customer name who have no orders