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

![Screenshot (13)](https://user-images.githubusercontent.com/64422457/85552431-9dcf6b80-b640-11ea-8cef-befd6e1cd915.png)

**UPLOAD FILE TO HDFS**

SO FIRST WE NEED TO CHANGE DIRECTORY TO THAT FOLDER WHERE OUR FILES IS PRESENT AND AFTER THAT WE CAN PUT INTO OUR REQUIRED FOLDER

CODE=cd /labs/Lab2.1/'

hdfs dfs -put data.txt test/

![Screenshot (14)](https://user-images.githubusercontent.com/64422457/85553220-601f1280-b641-11ea-8631-a821b683adff.png)

**COPY FILE**

TO COPY FILE FROM TEST TO ANOTHER FOLDER USE -cp

CODE=hdfs dfs -cp test/data.txt test/test1/data2.txt

![Screenshot (15)](https://user-images.githubusercontent.com/64422457/85554448-8a250480-b642-11ea-8922-2db44c0b695f.png)

**VIEW CONTENT OF FILES**

CODE=hdfs dfs -cat test/data.txt

the above code will give you whole data of file

to see the some ending data of files use below code

CODE=hdfs dfs -tail test/data.txt

![Screenshot (16)](https://user-images.githubusercontent.com/64422457/85555344-70d08800-b643-11ea-9375-4ec79d97c97a.png)

**MERGE TWO FILES INTO SINGLE FILE**

FIRST PUT THE NEW FILE INTO TEMP FOLDER BY USING ABOVE PUT FILE CODE AND THEN USE BELOW MERGE CODE

CODE=hdfs dfs -getmerge test /tmp/merged.txt

![Screenshot (17)](https://user-images.githubusercontent.com/64422457/85556725-c0638380-b644-11ea-9f91-1d2f760e1a37.png)










 





