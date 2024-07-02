## **Pizza Sales Project**

## Overview

This project presents an analysis of pizza sales using SQL queries. The primary aim is to derive insights from the sales data, such as total orders, revenue, most popular pizza sizes, and more. The project is designed to help promote business by offering a clear and comprehensive sales report.

# Contents

1. $\color{Blue}{Project\ Description}$ 
2. $\color{Blue}{Database\ Scheman}$ 
3. $\color{Blue}{SQL\ Queries}$
4. $\color{Blue}{Analysis}$
5. $\color{Blue}{Contributors}$

   
# Project Description
   
   This project involves using SQL queries to answer various questions related to pizza sales. The main objectives include:

1. Retrieving the total number of orders placed.
2. Calculating the total revenue generated from pizza sales.
3. Identifying the highest-priced pizza.
4. Determining the most common pizza size ordered.
5. Listing the top 5 most ordered pizza types along with their quantities.
6. Finding the total quantity of each pizza category by joining necessary tables.
7. Analyzing the distribution of orders by the hour of the day.
8. Finding the category-wise distribution of pizzas.
9. Calculating the average number of pizzas ordered per day.
10. Determining the top 3 most ordered pizza types based on revenue.
11. Calculating the percentage contribution of each pizza type to total revenue.
12. Analyzing the cumulative revenue generated over time.
13. Determining the top 3 most ordered pizza types based on revenue for each pizza category.

    
# Database Schema
 The project uses a structured database to store and manage pizza sales data. The database schema includes various tables that capture details of orders, pizza types, prices, and categories.

 ![Screenshot 2024-06-30 151156](https://github.com/aniketkumares/Pizza_sales/assets/120242082/f83d49e6-9714-4734-92f4-6e6779036c31)


# SQL Queries
 The analysis was conducted using the following SQL queries:

1. Total Number of Orders: SELECT COUNT(*) FROM orders;
2. Total Revenue: SELECT SUM(price) FROM sales;
3. Highest Price Pizza: SELECT MAX(price) FROM pizzas;
4. Most Common Pizza Size: SELECT size, COUNT(*) FROM orders GROUP BY size ORDER BY COUNT(*) DESC LIMIT 1;
5. Top 5 Most Ordered Pizzas: SELECT pizza_name, COUNT(*) FROM orders GROUP BY pizza_name ORDER BY COUNT(*) DESC LIMIT 5;
6. Total Quantity by Category: SELECT category, SUM(quantity) FROM orders JOIN pizzas ON orders.pizza_id = pizzas.id GROUP BY category;
7. Distribution by Hour: SELECT HOUR(order_time), COUNT(*) FROM orders GROUP BY HOUR(order_time);
8. Category-wise Distribution: SELECT category, COUNT(*) FROM orders JOIN pizzas ON orders.pizza_id = pizzas.id GROUP BY category;
9. Average Orders per Day: SELECT DATE(order_date), AVG(quantity) FROM orders GROUP BY DATE(order_date);
10. Top 3 Pizzas by Revenue: SELECT pizza_name, SUM(price) FROM sales GROUP BY pizza_name ORDER BY SUM(price) DESC LIMIT 3;
11. Percentage Contribution to Revenue: SELECT pizza_name, (SUM(price) / (SELECT SUM(price) FROM sales)) * 100 AS percentage FROM sales GROUP BY pizza_name;
12. Cumulative Revenue Over Time: SELECT DATE(order_date), SUM(price) OVER (ORDER BY DATE(order_date)) FROM sales;
13. Top 3 Pizzas by Revenue per Category: SELECT category, pizza_name, SUM(price) FROM sales JOIN pizzas ON sales.pizza_id = pizzas.id GROUP BY category, pizza_name ORDER BY category, SUM(price) DESC LIMIT 3;


# Analysis
 The SQL queries provided above help in understanding various aspects of pizza sales. The insights derived include the most popular pizzas, peak order times, revenue distribution, and more.

# Contributors
     Aniket Kumar
Thank you for checking out this project! If you have any questions or suggestions, feel free to contact us or open an issue.
