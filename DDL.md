
DDL is a subset of SQL used to define and manage the structure of database objects. It consists of commands that allow you to create, modify, and delete database objects such as tables, indexes, views, and constraints.

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

