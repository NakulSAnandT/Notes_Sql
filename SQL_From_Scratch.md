Mysql_root_password : Nakul@123

## Database Creation, Selection, Deletion
1. create database *database name* - **Creates a database**
2. create database if not exists *database name*- **Won't return an error if the same database exists**
3. use *database_name* - **To specify which database to use**
4. show databases - **To see all databases present**
5. drop database *database_name* 

## Types of data language

 - Data Definition Language
	It consists of SQL statements used to define and manage the structure of the database objects, such as tables, views, indexes, and schemas. DDL statements do not manipulate the actual data within the database
		**Create, Truncate, Alter, Delete**

-  DML - Data Manipulation Language
	It includes SQL statements used to retrieve, insert, update, and delete data within the database
		**Select, Insert, Update, Delete**

-  DCL - Data control language
	The commands are used to control security and concurrent access to table data
		**Grant, Revoke**






## DDL 

**Creating a table :**

1. create table ***table_name*** ( ***column_name*** datatype, ***column_name 2*** datatype)

    example : create table students (
			roll_no bigint primary key,
            student_name varchar(20),
            age int ,
            gender char(1),
            hobbies varchar(60)
         );

  *note : use ' ' to make a name single than using delimiter, ex : 'student name' varchar(20)*
  
**Truncating a table :** 

2. truncate ***table_name***  

**Dropping a table :** 

3. drop table ***table_name***

**Adding a new column :** 

4. alter table ***table_name*** alter add column ***column_name***  
    after/before ***column name***
 example : ALTER TABLE students ADD COLUMN Mobile2 bigint after student_name
 
  we can use after/before to specify where to add the new column 

**Modifying a column :** 

5.  alter table ***table_name*** alter modify ***column_name*** ***specifier***  
	example : alter table students modify Mobile2 varchar(10)


**Renaming a column :** 

6. alter table ***table_name*** change ***old_column_name new_column_name specifier*** 
	example : alter table students modify Mobile2 varchar(10)

**Renaming a table :** 

7. alter table ***table_name*** rename to ***new_table_name*** (Renaming a whole table)
	example : alter table students rename to student




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

## DDL:

1. GRANT SELECT, INSERT, UPDATE ON employees TO user1;
2. REVOKE DELETE ON employees FROM user2;
