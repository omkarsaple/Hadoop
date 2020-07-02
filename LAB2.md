**HERE WE LEARN ABOUT SQOOP**

1.What is sqoop?
Sqoop is a tool designed to transfer data between Hadoop and relational database servers.
It is used to import data from relational databases such as MySQL, Oracle to Hadoop HDFS, and export from Hadoop file system to relational databases. 

**SQOOP IMPORT**

Sqoop import used to import data from relational databases such as MySQL, Oracle to Hadoop HDFS, and export from Hadoop file system to relational databases. 

**MAKE SURE THAT YOUR HDFS IS CONNECTED TO RDS SO THAT YOU CAN PERFORM FOLLOWING OPERATIONS**

Example:Lets import data from mysql to HDFS

STEP 1:Create table in mysql or you can use existing one

**create table employe ( PersonID varchar,name char,salary double,city varchar);

STEP 2:Use Sqoop Import Command To Import Database:

**sqoop import --connect jdbc:mysql://your hostname/omkar(your Database name) --(your username of mysql)--(your password of mysql) --table employe(your tablename)**


