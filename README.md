# SQL-TASK2.0
# TASK4
# Introduction
Danny seriously loves Japanese food so at the beginning of 2021, he decides to embark upon a risky venture and opens up a cute little restaurant that sells his 3 favorite foods: **sushi**,  **curry**, and **ramen**.
Danny’s Diner needs your assistance to help the restaurant stay afloat - the restaurant has captured some very basic data from its few months of operation but has no idea how to use its data to help them run the business.
# Problem Statement
Danny wants to use the data to answer a few simple questions about his customers, especially about their visiting patterns, how much money they’ve spent, and also which menu items are their favorite. Having this deeper connection with his customers will help him deliver a better and more personalized experience for his loyal customers.
He plans on using these insights to help him decide whether he should expand the existing customer loyalty program - additionally, he needs help to generate some basic datasets so his team can easily inspect the data without needing to use SQL.
Danny has provided you with a sample of his overall customer data due to privacy issues - but he hopes that these examples are enough for you to write fully functioning SQL queries to help him answer his questions!
Danny has shared with you 3 key datasets for this case study:**members, menu and sales**
# A View of the Tables
![](Tables.png)
# Case Study Questions
Each of the following case study questions can be answered using a single SQL statement:
1.	What is the total amount each customer spent at the restaurant?
2.	How many days has each customer visited the restaurant?
3.	What was the first item from the menu purchased by each customer?
4.	What is the most purchased item on the menu and how many times was it purchased by all customers?
5.	Which item was the most popular for each customer?
6.	Which item was purchased first by the customer after they became a member?
7.	Which item was purchased just before the customer became a member?
8.	What are the total items and amount spent for each member before they became a member?
9.	If each $1 spent equates to 10 points and sushi has a 2x points multiplier - how many points would each customer have?
10.	In the first week after a customer joins the program (including their join date) they earn 2x points on all items, not just sushi - how many points do customers A and B have at the end of January?
11.	# Skills Involved
Use of SUM FUNCTION
Use of SELECT (DISTINCT)
Use of SELECT (WHERE) 
Use of AS
Use of ON
Use of JOIN Clause
Use of GROUP BY clause
Use of COUNT Function
Use of SUBQUERY
Use of ORDER BY Statement
Use of RANK
Use of CASE Statement
#  Visaul Display of the Procedure For Questions 1 to 6
![](SQL1.png)
To get the total amount each customer spent at the restaurant, I JOIN the sales table with the menu table, SUM the price column, name it AS Total¬ Amount, and SELECT DISTINCTly.
![](Q1.png)
The next question is to get the number of days each customer visited the restaurant. I did a DISTINCT COUNT of the order date and named the new column No. of Days, GROUP IT BY customer id, and SELECT the customer id.
![](Q2.png)
I found the first item each customer purchased from the menu by JOINING the sales and menu tables WHERE the order date is equal to the customer’s first day of visiting the restaurant (2021-01-01)  and then SELECTED all columns. 
![](Q3.png)
  Also, the most purchased item on the menu and the number of times all customers purchased it was calculated thus: I joined the sales and menu tables, COUNTED  the names of each purchased product, SELECTED the product name, and filtered by same product name and sort in ASCENDING (ASC) order.
![](Q4.png)
 To get the most purchased product by each customer, I JOINED the sales and menu tables, COUNTED the customer id and named it unit and then I SELECTED customer id and product name filter by same columns and sorted by customer id in ASCENDING (ASC) order.
![](Q5.png)
I found the first item purchased by the customers after they became a member by JOINING the three tables; sales, menu, and members tables. Then I RANKED the customer id column, ORDERED by join date column and name it FIRST PRODUCT. After which I SELECTED customer id, join date, and product name, and GROUPED BY the same columns.
![](Q6.png)
#  Visaul Display of the Procedure For Questions 7 to 10
![](SQL2.png)
I found the item purchased by the customers just because they became members by JOINIG the sales and members tables. I used the WHERE clause to restrict the order date to dates that were less than or equal to 2021-01-09 which is when the last member joined. Then I SELECT customer id, product name, order date and SORTED BY order date.
![](Q7.png)
 I obtained the total item and amount spent by each customer before they became members by JOINING the three tables again and used the WHERE clause to restrict the order date to exclude the first membership date of 2021-01-07. Then I SUMMED UP the price and named it as Total Amount, COUNTED, and SELECTED the customer id. Thereafter, I  FILTERED BY customer id.
![](Q8.png)
To calculate each customer’s point given the condition, I JOINED the sales and menu tables and GROUP BY product name,  multiplied the prices WHEN the product name is ‘SUSHI’  and WHEN it wasn’t using the CASE FUNCTION and named the column POINTS OBTAINED. Then I SUMMED the POINTS OBTAINED, SELECTED customer id, and GROUPED BY the same column.
![](Q9.png)
For the last question, I got the points of both customers by JOINING the sales and menu tables, using a CASE statement to restrict the order date to less than or equal to ‘2021-01-07’ which is the earliest membership date, and then multiplicated the price by *20 ELSE multiply the price by *1 which will ensure the un referenced prices maintain their values and name the new column POINTS. I SUMMED UP the points and named them MONTHLY POINTS and filtered them by customer id. 
![](Q10.png)
 **I use MSSQL**, thanks for reanding. 


