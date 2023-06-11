A subquery, also known as an inner query or nested query, is a query that is embedded within another query. It allows you to use the result of one query as a part of another query, enabling you to perform complex operations and obtain more specific results. Subqueries are enclosed within parentheses and can be used in various parts of a SQL statement, such as the SELECT, FROM, WHERE, or HAVING clauses

ex : 
SELECT customer_name
FROM customers
WHERE customer_id IN (SELECT customer_id FROM orders WHERE total_amount > 200);
 Benefits:
 
- Subqueries provide flexibility and enable you to perform
advanced filtering, grouping, and aggregations based on intermediate results. 
- They can simplify complex queries by breaking them down into smaller, more understandable parts.
- Subqueries enhance the readability and maintainability of queries by organizing them logically.