**HERE WE LEARN ABOUT SQOOP**

1.What is sqoop?
Sqoop is a tool designed to transfer data between Hadoop and relational database servers.
It is used to import data from relational databases such as MySQL, Oracle to Hadoop HDFS, and export from Hadoop file system to relational databases. 

**(1):SQOOP IMPORT**

Sqoop import used to import data from relational databases such as MySQL, Oracle to Hadoop HDFS, and export from Hadoop file system to relational databases. 

**MAKE SURE THAT YOUR HDFS IS CONNECTED TO RDS SO THAT YOU CAN PERFORM FOLLOWING OPERATIONS**

Example:Lets import data from mysql to HDFS

STEP 1:Create table in mysql or you can use existing one

**create table employe ( PersonID varchar,name char,salary double,city varchar);

STEP 2:Use Sqoop Import Command To Import Database:

**sqoop import --connect jdbc:mysql://your hostname/omkar(your Database name) --(your username of mysql)--(your password of mysql) --table employe(your tablename)**

by using the above command your database get import which looks like following image

![Screenshot (19)](https://user-images.githubusercontent.com/64422457/86376166-364e9700-bca4-11ea-92b5-e8c391e1afa1.png)


STEP 3:You can import selected columns also from your database by using --column command and by specifying target directory


**sqoop import --connect jdbc:mysql://your hostname/omkar(your Database name) --(your username of mysql)--(your password of mysql) --table employe(your tablename) --columns salary,name --target-dir salaries_name**

![Screenshot (50)](https://user-images.githubusercontent.com/64422457/86376774-22effb80-bca5-11ea-935f-235f41f6d150.png)

STEP 4:Now we use --split by command to split our data based on gender column also we will use --query command with where column

**NOTE=While importing record we will encounter so use import command with following command "-Dorg.apache.sqoop.splitter.allow_text_splitter="true"1**

**sqoop import "-Dorg.apache.sqoop.splitter.allow_text_splitter="true"1 --connect jdbc:mysql://your hostname/omkar(your Database name) --(your username of mysql)--(your password of mysql) --query "select * from employe where salary>20000 AND \$CONDITIONS --split by gender -m 2 --target-dir salaries_gender**

![Screenshot (51)](https://user-images.githubusercontent.com/64422457/86377961-ac53fd80-bca6-11ea-975f-03a1a396468b.png)


**(2):SQOOP EXPORT**

Sqoop Exoprt is used to export data back from the HDFS to the RDBMS database.

Lets Take An Example,

STEP 1:lets make directory in HDFS by following Command

**hdfs dfs -mkdir salarydata**

STEP 2:Put the created data into salarydata.txt to HDFS directory salarydata

**COMMAND=hdfs dfs -put salarydata.txt salarydata**

![Screenshot (52)](https://user-images.githubusercontent.com/64422457/86378869-c5a97980-bca7-11ea-97be-ece6aaec0fc2.png)

STEP 3:create table in mysql 

create table salaries_kp(gender char,age int,salary double,zipcode int);

STEP 4:Export the data

**sqoop export --connect jdbc:mysql://your hostname/omkar(your Database name) --(your username of mysql)--(your password of mysql) --table salaries_kp --export-dir salarydata.txtx --input-fields-terminated-by ","**

![Screenshot (53)](https://user-images.githubusercontent.com/64422457/86379949-24bbbe00-bca9-11ea-8e35-e3b768943d8a.png)

verify your output in mysql

![Screenshot (49)](https://user-images.githubusercontent.com/64422457/86380008-39985180-bca9-11ea-9456-019f00276961.png)









