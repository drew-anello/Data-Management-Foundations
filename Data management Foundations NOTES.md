

## DBMS (Data Base management system)
- A special software program that helps users create and maintain a database 
	- Makes it easy to manage large amounts of information
	- Handles Security
	- Backups
	- importing exporting data
	- concurrency (the ability of a system to handle multiple tasks at the same time)
	- interacts with software applications
		- Programming Languages

DBMS will interact with the website to create read update and delete information. 

### Relational Database (SQL)

- Organizes Data into one or more tables
	- Each table has columns and rows
	- A unique Key identifies each row



Built in tables

 
 ##### Student Table

| *ID #* | Name |  Major |  
| -------: | :------: | :------ |  
| 1 | Jack | Biology |  
|2 | Kate | Sociology |
|3 | Claire | English |
|4 | John | Chemistry |


### Relational Database Management System (RDBMS)

- Helps users create and maintain a relational database 
	- *Examples* 
		- MySQL Oracle, PostgreSQL MariaDB etc. 


#### Structured Query Language (SQL) 

- the language used to interact with RDBMS (a relational database)




##### Queries

- requests made to the database management system for specific information



# Tables and Keys

#### STUDENT TABLE

| ==*Student ID*== | Name |  Major |  
| -------: | :------: | :------ |  
| 1 | Jack | Biology |  
|2 | Kate | Sociology |
|3 | Claire | English |
|4 | John | Chemistry |

- Tables have columns (vertical) and rows (horizontal) 
- columns represent a single attribute i.e age, name , major, id 
- row represents single entry i.e 1, jack , biology
- Always need a special column called primary key
- in this case student id is a unique attribute
  
  
  ### Surrogate Key 

- is key that has no mapping to anything in the real world
- emp_id is the Surrogate Key in this case


|==emp_id==|first_name|last_name|birth_date|sex|salary|
|--:|:-:|:-:|:-:|:-:|:--|
|100|Jan|Levinson|1961-05-11| F|110,000 | 
|101|Michael|Scott|1964-03-15| M|75,000 |
|102|Jim|Halpert|1981-06-13| M|80,000 | 
|103|Angela|Martin|1973-08-14| F|72,000 | 


### Natural Key

- key that has a mapping to real world
- in this case emp_ssn is the primary key ssn being their social security number


|==emp_ssn==|first_name|last_name|birth_date|sex|salary|
|--:|:-:|:-:|:-:|:-:|:--|
|123456789|Jan|Levinson|1961-05-11| F|110,000 | 
|555662888|Michael|Scott|1964-03-15| M|75,000 |
|111333999|Jim|Halpert|1981-06-13| M|80,000 | 
|998877665|Angela|Martin|1973-08-14| F|72,000 | 



### Foreign Key 

- stores the primary key of a row in a separate database table
- in this example there is a separate database table of all the dunder mifflin branches, in the employee table has their uses the primary key from the branch table (branch_id) and adds it to the the db table

**Employee**

|==emp_ssn==|first_name|last_name|birth_date|sex|salary| branch_id|
|--:|:-:|:-:|:-:|:-:| :-:|:--|
|123456789|Jan|Levinson|1961-05-11| F|110,000 |1 |
|555662888|Michael|Scott|1964-03-15| M|75,000 | 2|
|111333999|Jim|Halpert|1981-06-13| M|80,000 | 3| 
|998877665|Angela|Martin|1973-08-14| F|72,000 | 2|


**Branch**

| ==*branch_id*== | branch_name |  mgr_id |  
| -------: | :------: | :------ |  
| 2 | Scranton | 101 |  
|3 | Stamford | 102 |
|1 | Corporate | 108 |


#### Composite Key

A key that needs 2 attributes.
