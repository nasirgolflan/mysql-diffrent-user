# mysql-diffrent-user

# Create a new MySQL User Account

     CREATE USER 'newuser'@'%' IDENTIFIED BY 'user_password';
     CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'user_password';
     CREATE USER 'newuser'@'10.8.0.5' IDENTIFIED BY 'user_password';

# Grant Privileges to a MySQL User Account

The most commonly used privileges are:

    ALL PRIVILEGES – Grants all privileges to a user account.
    CREATE – The user account is allowed to create databases and tables.
    DROP - The user account is allowed to drop databases and tables.
    DELETE - The user account is allowed to delete rows from a specific table.
    INSERT - The user account is allowed to insert rows into a specific table.
    SELECT – The user account is allowed to read a database.
    UPDATE - The user account is allowed to update table rows.
    
syntax     

    GRANT CREATE, DELETE, INSERT, SELECT, UPDATE  ON database_name.table_name TO 'database_user'@'localhost';
    
    GRANT ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';

    SHOW GRANTS FOR 'database_user'@'localhost';

# Revoke Privileges from a MySQL User Account

    REVOKE ALL PRIVILEGES ON database_name.* FROM 'database_user'@'localhost';

# Remove an Existing MySQL User Account

    DROP USER 'user'@'localhost'
    
# ShortCut

     create database testDB;

     CREATE USER 'test2user'@'%' IDENTIFIED BY 'test2pass';

     GRANT CREATE, DELETE, INSERT, SELECT, UPDATE  ON testDB.* TO 'test2user'@'%';

     SHOW GRANTS FOR 'test2user'@'%';

     exit;

# MySQL 8 Confirm MySQL version
     mysql -V
     sudo mysql --user=root mysql
     UPDATE mysql.user SET authentication_string=null WHERE User='root';
     flush privileges;
     ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password_here';
     flush privileges;
     exit
 # MySQL 5.7 
     
     update user set authentication_string=PASSWORD('your_password_here') where user='root';
     update user set plugin="mysql_native_password" where User='root';
     flush privileges;
     exit
     
    
 # MySQL 5.6 
 
     update user set Password=PASSWORD('your_password_here') where user='root';
     update user set plugin="mysql_native_password" where User='root';
     flush privileges;
     exit
