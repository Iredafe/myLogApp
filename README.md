# myLogApp
Springboot RESTful Web Service application built to consume, store, and process logs from a front-end application and to make the stored logs retrievable for batch processing. The aim of this project is to develop an algorithm that is callable through a RESTful API endpoint in Java.



DOCUMENTATION

Name of SpringBoot REST application: I named the application "applogger".

Problem Statement:

Create a RESTful Web Service to consume, store, and process logs from a 
frontend application and to make the stored logs retrievable for batch processing.

Solution Approach:

In order to build the application well, I created three tables in MySql
with database named "log_directory". These tables are named "log", "action" and "properties".
These three tables are linked together with foreign key relationships.

The username and password of the database can be found in application.properties file 
under the src/main/resources directory. 

So far, It has five packages in src/main/java directory namely:
1. com.dafe.spring.applogger
2. com.dafe.spring.applogger.dao
3. com.dafe.spring.applogger.entity
4. com.dafe.spring.applogger.rest
5. com.dafe.spring.applogger.service

1. com.dafe.spring.applogger:

The first package contains the AppLoggerApplication class which is the springboot 
class with a main method from which the application can be run.

2. com.dafe.spring.applogger.dao:

The application uses the DAO design pattern hence the dao package contains so far, 
the UserLogDAO class and the UserLogDaoHibernateImplementation class().

3. com.dafe.spring.applogger.entity:

The entity package contains the classes that maps with the Hibernate and mySql tables.
These classes are UserLog, Action, Properties. 

Based on the sample log given in the test requirement, 
I decided to create three entity classes. These are named 
UserLog, Action, Properties. These entity classes are to be mapped 
to the database "log_directory", using Hibernate advanced @OneToMany bi-directional 
mapping(for log and action table) and @OneToOne mapping(for action and properties table).




The UserLog entity contains fields that maps with columns in mysql table with the name "log".

The Action entity class contains fields that maps with columns in mysql table "action"

While the Properties entity class contains fields that maps with columns in mysql table "action"

4. com.dafe.spring.applogger.rest: 
the rest package contains the rest controller class  

5. com.dafe.spring.applogger.service: 

this package contains the service layer. The service layer is included to 
help define the application boundaries.It contains application's business logic, controlling transactions and coor-dinating 
responses in the implementation of its operations. 


To test the application for Get Method call on the browser, use http://localhost:8080/api/userLog


The sql file is attached to the repository as a .sql extension script. You would need to download it and run 
the query in mySql workbench to test the springboot application.


Answer to Follow-Up Question

I would make the solution cloud scalable by incorporating it with a cloud serverless network like firebase
which helps manage complex infrastructure and gives functionality like analytics, databases and crash reporting.
