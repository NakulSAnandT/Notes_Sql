A _window function_ performs a calculation across a set of table rows that are somehow related to the current row. This is comparable to the type of calculation that can be done with an aggregate function. But unlike regular aggregate functions, use of a window function does not cause rows to become grouped into a single output row — the rows retain their separate identities. Behind the scenes, the window function is able to access more than just the current row of the query result.

------------------------------------------------------
- select avg(salary) from employee -  A single result 

op:

35125.000000

- select dno,avg(Salary) from employee - Avg salary of each department
op:

| 1 | 55000.000000 |
|---|--------------|
| 4 | 31000.000000 |
| 5 | 33250.000000 |

- select dno,avg(salar) over() from employee - you'll get the whole row even with the same output 

op:

| 5 | 35125.000000 |
|---|--------------|
| 5 | 35125.000000 |
| 5 | 35125.000000 |
| 5 | 35125.000000 |
| 1 | 35125.000000 |
| 4 | 35125.000000 |
| 4 | 35125.000000 |
| 4 | 35125.000000 |

---------------------------------------------------
- The "OVER (PARTITION BY)" clause in SQL is used to divide the result set into partitions or groups based on one or more columns. It allows you to perform calculations or aggregations on each partition separately, providing more granular control over the grouping and aggregation process.
- Over(Partition by 'columnname') is like groupby except it doesnt print each of the unique row. it prints all of them

- example : 

select dno,fname,ssn, count(dno) over() from employee 

| 5 | John     | 123456789 | 8 |
|---|----------|-----------|---|
| 5 | Franklin | 333445555 | 8 |
| 5 | Joyce    | 453453453 | 8 |
| 5 | Ramesh   | 666884444 | 8 |
| 1 | James    | 888665555 | 8 |
| 4 | Jennifer | 987654321 | 8 |
| 4 | Ahmad    | 987987987 | 8 |
| 4 | Alicia   | 999887777 | 8 |

- example with Partition By

select dno,fname,ssn, count(dno) over(partition by dno) from employee

| 1 | James    | 888665555 | 1 |
|---|----------|-----------|---|
| 4 | Jennifer | 987654321 | 3 |
| 4 | Ahmad    | 987987987 | 3 |
| 4 | Alicia   | 999887777 | 3 |
| 5 | John     | 123456789 | 4 |
| 5 | Franklin | 333445555 | 4 |
| 5 | Joyce    | 453453453 | 4 |
| 5 | Ramesh   | 666884444 | 4 |

-------------------------------------------------------
when to use window?

- To find running averages / Moving average
- Running total orders
- Rank
- Percentile
- When you want measure trends or changes over row
- To rank a column for outreach/prioritization

---------------------------------------------------- 
RANK 

select
	dno,ssn,salary,sex,
    rank() over(order by salary desc) as Sal_rank,
    rank() over(partition by sex order by salary desc) as gender_based_sal_rank
from employee		


| 4 | 987654321 | 43000.00 | 2 | F | 1 |
|---|-----------|----------|---|---|---|
| 5 | 453453453 | 25000.00 | 6 | F | 2 |
| 4 | 999887777 | 25000.00 | 6 | F | 2 |
| 1 | 888665555 | 55000.00 | 1 | M | 1 |
| 5 | 333445555 | 40000.00 | 3 | M | 2 |
| 5 | 666884444 | 38000.00 | 4 | M | 3 |
| 5 | 123456789 | 30000.00 | 5 | M | 4 |
| 4 | 987987987 | 25000.00 | 6 | M | 5 |


Here the sal_rank column just ranks the column accordingly, but gender based sal rank column, takes each genders, and give rank to each of them , we can see M has rank 1,2,3,4,5 and F has 1,2,2. That means the partition by func partitions the genders and then rank them by their salary.

REFER 103.sql

Rank()- ranks like 1,2,2,4,5,6,7,7,9 (The rank 2 is divided into two then rank 3 is avoided)

dense_rank() - ranks like 1,2,2,3,4,5,6,7,7,8

row_number()- running row count 1,2,3,4,5,6,7,8 