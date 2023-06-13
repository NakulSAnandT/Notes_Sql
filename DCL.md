
DCL stands for Data Control Language in SQL. It consists of a set of commands used to control access and permissions on database objects. DCL commands are primarily used to grant or revoke privileges, manage user roles, and control security within a database. Here are some commonly used DCL commands:

1. GRANT:

- The GRANT command is used to grant specific privileges to users or roles.
    
- Example: Granting SELECT privilege on a table to a user:

	- GRANT SELECT ON table_name TO user_name;
-------------------------------------------------------
2. REVOKE DELETE ON employees FROM user2;

- The REVOKE command is used to revoke previously granted privileges from users or roles.
    
- Example: Revoking INSERT privilege on a table from a user:
	- REVOKE INSERT ON table_name FROM user_name;
-------------------------------------------------------
3. CREATE USER:

- The CREATE USER command is used to create a new user account in the database.
    
- Example: Creating a new user with a password:
	- CREATE USER user_name IDENTIFIED BY 'password';
