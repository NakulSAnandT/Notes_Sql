1. **Comparison Operators:**
- Equal to: =
	ex: SELECT * FROM products WHERE name = 'iPhone 12';
- Not equal to: <>
	ex: SELECT * FROM products WHERE price <> 799;
- Greater than: >
	ex: SELECT * FROM products WHERE price > 800;
- Less than: <
	ex: SELECT * FROM products WHERE price < 900;
- Greater than or equal to: >=
- ex: SELECT * FROM products WHERE price >= 750;
- Less than or equal to: <=
	ex: SELECT * FROM products WHERE price <= 799;

2. **Logical Operators:**
- AND: Used to combine multiple conditions where all must be true.
	ex: SELECT * FROM employees WHERE salary > 5000 AND name LIKE 'J%';
- OR: Used to combine multiple conditions where at least one must be true.
	ex: SELECT * FROM employees WHERE salary < 5500 OR name = 'Sarah';
- NOT: Negates a condition or reverses the logical result.
	ex : SELECT * FROM employees WHERE NOT salary > 6000;
;

3. **String Operators:**:
- Concatenation: Concatenates two or more strings using the || or CONCAT operator.
- LIKE: Used for pattern matching in strings.
	ex : SELECT * FROM employees WHERE name LIKE 'J%';
- IN: Checks if a value exists in a specified set of values.
	ex: select fname,lname from employee where fname in ('Alicia','Zelaya') 
	
4. **NULL-related Operators:**
- IS NULL: Checks if a value is NULL. 
	ex : SELECT * FROM employees WHERE age IS NULL
- IS NOT NULL: Checks if a value is not NULL.
	ex: SELECT * FROM employees WHERE age IS NOT NULL;

5. **Aggregate Functions Operators:**
- COUNT: Returns the number of rows. 
- SUM: Calculates the sum of a column. 
- AVG: Calculates the average of a column. 
- MIN: Returns the minimum value of a column. 
- MAX: Returns the maximum value of a column.
	ex:SELECT SUM(salary) FROM employees;



## wildcard

% - A% (Name that starts with A)
_ - A___(Name that starts with A and 4 letters rest)

