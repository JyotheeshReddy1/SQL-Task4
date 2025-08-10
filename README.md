# SQL-Task4

--Task 4: Aggregate Functions and Grouping

-- Table: sales
-- Columns: id, product_name, category, quantity, price, sale_date

-- 1. Total sales amount (SUM) for all products
SELECT SUM(quantity * price) AS total_sales
FROM sales;

-- 2. Count total orders
SELECT COUNT(*) AS total_orders
FROM sales;

-- 3. Average quantity per order
SELECT AVG(quantity) AS avg_quantity
FROM sales;

-- 4. Group by category with total sales per category
SELECT category, SUM(quantity * price) AS category_sales
FROM sales
GROUP BY category;

-- 5. Group by product name with total quantity sold
SELECT product_name, SUM(quantity) AS total_quantity
FROM sales
GROUP BY product_name;

-- 6. Average price per category
SELECT category, AVG(price) AS avg_price
FROM sales
GROUP BY category;

-- 7. Filter grouped results using HAVING
-- Example: categories where total sales > 500
SELECT category, SUM(quantity * price) AS category_sales
FROM sales
GROUP BY category
HAVING SUM(quantity * price) > 500;

-- 8. Count number of products per category
SELECT category, COUNT(DISTINCT product_name) AS product_count
FROM sales
GROUP BY category;
