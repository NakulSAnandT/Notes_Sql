A subquery, also known as an inner query or nested query, is a query that is embedded within another query. It allows you to use the result of one query as a part of another query, enabling you to perform complex operations and obtain more specific results. Subqueries are enclosed within parentheses and can be used in various parts of a SQL statement, such as the SELECT, FROM, WHERE, or HAVING clauses

**ex :** 
	
	SELECT customer_name
	FROM customers
	WHERE customer_id IN (SELECT customer_id FROM    orders WHERE total_amount > 200);

**Benefits:**
 
- Subqueries provide flexibility and enable you to perform
advanced filtering, grouping, and aggregations based on intermediate results. 
- They can simplify complex queries by breaking them down into smaller, more understandable parts.
- Subqueries enhance the readability and maintainability of queries by organizing them logically.

![[Subqueries_1.png]]

- Firstly we are selecting Dno,avg salary from employee table then is group by with dno as there is an aggregation function.
- Now we need min and max avg salary.
- To do that we use subquery where we select min and max of avg salary column (which we have created using avg() from employee table).
- It might throw an error if you didn't give an alias for the part of selection(ie. in this code we have used "as Dept_average").

**ex 2** : 

select fname,lname,ssn 
from employee
where salary >
(select avg(salary) as avg_salary from employee
) 

This code selects the first name, last name and ssn who has salary greater than the average salary using subquery