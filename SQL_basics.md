Mysql_root_password : Nakul@123

## Database Creation, Selection and Deletion
1. create database *database name* - **Creates a database**
2. create database if not exists *database name*- **Won't return an error if the same database exists**
3. use *database_name* - **To specify which database to use**
4. show databases - **To see all databases present**
5. drop database *database_name* 

## Types of data language

 - Data Definition Language [[DDL]]
	It consists of SQL statements used to define and manage the structure of the database objects, such as tables, views, indexes, and schemas. DDL statements do not manipulate the actual data within the database
		**Create, Truncate, Alter, Delete**

-  DML - Data Manipulation Language[[DML]]
	It includes SQL statements used to retrieve, insert, update, and delete data within the database
		**Select, Insert, Update, Delete**

-  DCL - Data control language [[DCL]] 
	The commands are used to control security and concurrent access to table data
		**Grant, Revoke**


