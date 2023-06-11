## DML 

1. Selection:

-  select ***column_name1***,***column_name*** from ***table_name***
-  select * from ***table_name***
-  select ***column_name*** from ***table_name*** where ***condition***
	ex : select fname,lname from employee where Gender = 'M'
- we can use multiple operators in the selection statement [[Operators in sql]]

2. Insertion : 

- insert into ***table_name*** (column1,column2,column3) Values('a',123,'c')

3. Updation :
- update ***table_name*** SET ***column1 = value1*** where condition
	ex : update employee set salary = 50000 where fname like '%a' and id = 101
	ex: update employee set salary = 0 where salary is null

4. Deletion:
- delete from ***table_name*** where condition
	delete from employee where salary >=90000