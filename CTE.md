- CTE stands for Common Table Expression. It is a temporary named result set that you can reference within a SELECT, INSERT, UPDATE, or DELETE statement. CTEs are useful when you want to break down complex queries into smaller, more manageable parts or reuse a subquery multiple times within a query.

- They are defined using WITH clause 

- We can specify multiple temp tables using with clause
	 ex : with **avg_salary** as 
	        (select dno,avg(salary) from employee 
	        group by dno), **Total_hours** as(select dno,sum(hours) from employee group by dno))


EX : 

with temp_table as( 
select essn,sum(hours) as total_hours from works_on
group by essn
)

select fname,lname,bdate,address,total_hours from employee
inner join temp_table on employee.ssn = temp_table.es

Explanation : 

- Here i have created a table called  "Temp_table" which contains essn and sum of hours which is labelled under
  "total_hours" from works_on table.
- Then i'm selecting fname,lname, address, bdate, total_hours from employee table which is inner joined with the temporary table i have made.
- Making it easier to group different insights together and not having to actually use the whole table!