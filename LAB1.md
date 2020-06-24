**CREATE DIRECTORY IN HDFS**


CODE=hdfs dfs -ls /

![Screenshot (4)](https://user-images.githubusercontent.com/64422457/85548848-fbfa4f80-b63c-11ea-905d-94a24aadad52.png)


**CREATE DIRECTORY**

CODE=hdfs dfs -mkdir test

TO CREATE MULTIPLE DIRECTORIES

CODE=hdfs dfs -mkdire test/test2/test3

&

**TO VIEW THE CONTENTS OF FOLDER**

CODE=hdfs dfs -ls -R

![Screenshot (12)](https://user-images.githubusercontent.com/64422457/85549622-cc981280-b63d-11ea-8081-84145c2a5f06.png)

**DELETE DIRECTORY**

CODE=hdfs dfs -rm -R test/test2

