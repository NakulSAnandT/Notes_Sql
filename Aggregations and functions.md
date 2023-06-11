
Aggregation Lets you do calculations on multiple data and returns a single value 

ex: sum, avg, count etc.

- count()
	Count(expression) or Count(distinct 
	select count * from employee 
	select  count(column name) from employee
- Avg(),Sum(),Min(),Max()
	select aggregate(column name )
	from table name
	where condition 
- GroupBy()
  1.  Used to reduce the amount of code you wanna write,
  2.  any column in the select statement that isn't within an aggregator must be in GroupBy clause
  3. Always goes between where and order by
  4. for eg:
	i want average salary of my employees, i would have to filter (where gender == 'm' ) the for female too. to avoid that we can use GroupBy 

  5. **select sex,avg(Salary) as AverageSalary  
	from employee 
	where condition
	GroupBy sex** 
	
 6. This will categories the sex column into M and F so no need for repetation
	Also sex,avg(Salary) will only work if groupby is mentioned


- **Distinct** :
	works like unique() in python
	select distinct sex from employee 
	select count(distinct sex) from employee # works like nunique()
- **Having** :
	Used to filter the GroupBy results. comes after groupby. ex :
	i want to find average salary of departments which has more than 2000
	select dno,avg(Salary ) as average_salary 
	from employee 
	groupby dno 
	having average_salary > 2000
	note where can't use columns which are created after aggregation ( as 'column name')
- **Date functions** :
	-select extract(year from bdate) as year
	 from employee 
- **Case statements** :
	select ssn,
    case 
    when salary < 2000
     then "Less"
     when salary > 2000
     then "More"
     else "Equal"
     end as payscale
     from employee