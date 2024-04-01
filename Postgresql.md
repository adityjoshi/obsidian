
# **Start postgresql**
brew services start postgresql 

**To check the databases** => forward \

**Create a database** => CREATE DATABASE test;
**Delete a database** => drop database test;
**Connect to database** => forward \ c test

**Create a table** => create table Employee(name varchar(10),id int,primary key(id));
primary key => it tells how the stuff will be differentiated
forward  \\\ d employee to see the table 

## **Insert Data in table**
insert into student(rollno, name)values(1,'aditya');
### To insert multiple values at once
insert into student(rollno, name)values(1,'aditya'),(2,'pahadi');


## Select from database 
**To fetch all columns** => select * from students;
**To select distinct** => select distinct name from student;


## Where clause in database
