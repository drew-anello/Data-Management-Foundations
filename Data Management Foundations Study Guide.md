

## Basics and Systems

**Database Application** - software that helps businesses and users interact with a database system

**Database Roles** - Database admin is responsible for securing the data system against unauthorized users, the admin enforces procedures for user access and database system availability. 

**Authorization** - many users should have limited access to tables, roles, columns, rows of a database. Database System Auth allows users information within their scope.  

**Rules** - Database system ensures data is consistent with structural and business rules. 


## Architecture

**Query Processor** - intercepts queries creates a plan to modify the database or retrieve data and returns query results to the application. Query Processor performs **Query Optimization** to perform the most efficient instructions. 

**Storage Manager** - translates Query processor instructions into low level file systems command that modify or retrieve data. Database size range from megabytes to many terabytes so the storage manager users indexes to quickly locate data. 

**Transaction Manager** - Ensures Transactions are properly executed, transaction manager prevents conflicts between concurrent transaction, the transaction manager also restores the database to a consistent state in the event of a transaction or system failure. 


*Metadata* - is data about the database such as column names, and number of rows in each table


##### Relational Database 
- stores data in tables, columns and rows similar to a spreadsheet

- All relational Database systems support SQL (Structured Query Language)
  
- Relational Systems are ideal for databases that require an accurate record of every transaction such as banking, airline, reservation systems and student records. 

- Newer non relational databases are called NoSQL are 'not only SQL' and are optimized for big data. 
		- mongo db is is a NoSQL DB that is open source and is rated 5 in db engines 


## Query Languages 


Query - is a command for a database that typically inserts new data, retrieves data, updates data, or deletes data from a database. (CRUD)

  
#### SQL STATEMENT 

 SQL statement - is a database command such as a query that inserts, selects, updates, or deletes data

- **INSERT** inserts a row into a table

- **SELECT** retrieves data from a table

- **Update** Modifies data in a table

- **DELETE** deletes rows from a table. 



SQL CREATE TABLE statement creates a new table by specifying the table and column names, each column is assigned a data type that indicates the format of column values, Data types can be numeric, textual, or complex

- INT stores integer values
- DECIMAL stores fractional numeric values, 
- VARCHAR stores textual values
- DATE stores year, month and day


Some data types are followed by one or two numbers in parentheses to define the size of the data type 

example
- VARCHAR(10) = 10 characters
- DECIMAL(10) = 7 whole number characters and 3 after the decimal point  1234567.890
  
  
## Database Design and Programming


#### **Analysis** 
A database design is a specification of a database objects such as tables, columns data types and indexes Database Design also refers to the process used to develop the specification. 

1. Analysis
2. Logical design 
3. Physical design


Analysis Phase - specifics database requirements on a very high level.  Requirements are represented as entities, relationships, and attributes (ERD). 

- Entity is a person, place activity or thing, 

- Relationship is a link between entities 

- Attribute is a descriptive property of an entity. 
	
- *Analysis may also be called conceptual design, entity relation ship modeling and requirements definition*


#### Logical Design

defines the database requirements in database system, Converts entities, relationships and attributes into tables, keys and columns. 


#### Physical Design 

Adds indexes and specifies how tables are organized on storage media. 
- example - Rows of a table may be sorted on the values of a column and stored in order. 

Data Independence
- the principal that that physical design only affects query processing speed but not result. 
 - allows database designers to tune query performance without changes to application programs


To simplify use of SQL with a general purpose language, database programs typically use an API aka Application programming interface. 

##### ERD

- Rectangle represents Entity
- Lines between rectangles are relationships
- Text inside rectangles are attributes




## MYSQL 


#### MySQL Command line Client

- Text interface included in the MySQL server download

- WORLD database is usually installed with MySQL

-  MySQL server returns an error code and description when a sql statement is syntactically incorrect or the database cannot execute the statement 


## Relational Model


#### Database models

Database Model is a conceptual framework for database systems with three parts

**Data Structures** - prescribe how data is organized

Operations - manipulate data structures

**Rules** - govern valid data


#### Relational Data Structure

**Set** - an unordered collection of elements enclosed in braces ex: {a, b, c} and {c, b, a} are the same because sets are not ordered

**Tuple** - an ordered collection of elements enclosed in parentheses EX: (a, b, c) and (c, b, a) are different since tuples are ordered


**Data structures organize data in tables**

- Table has a name, a fixed tuple of columns and a varying set of rows
- Column has a name and a data type
- Row is an unnamed tuple of values, each value corresponds to a column and belongs to the columns data type
- data type is a named set of values from which column values are drawn


Synonyms 

- Table, File, Relation
- Row, Record, Tuple, 
- Column, Field, Attribute


#### Relational Operations

- Select - selects a subset of rows of a table
- Join - combines two tables by comparing related columns
- Union selects all rows of two tables
- Aggregate - computes functions over multiple table rows such as sum and count


**Rules are logical constraints that ensure data is valid.**




## Structured Query Language (SQL)


*SQL is the standard language for relational databases and is usually supported in non relational databases* 

Example of query and syntax

```sql 
SELECT Name FROM City WHERE Populatiopn > 1000;
```





|Type|Description|Examples|
|:------| :------------:|-----------:|
|Literals| Explicit Values that are string numeric or binary, Strings myst be surrounded by since or double quotes, Binary values are represented with x '0' where the 0 is any hex value | 'String',        "String"      123,          x'0fa2'|
|Keywords| Words with special meaning| SELECT, FROM, WHERE|
|Identifiers| Objects from the database like tables, columns, etc.| City, Name, Population |



#### SQL sublanguages 

- Data Definition Language (DDL) - Defines the structure of the database
- Data Query language (DQL) - retrieves data from the database
- Data Manipulation language (DML) - Manipulates data stored in a database
- Data Control Language (DCL) - Controls database user access 
- Data Transaction Language (DTL) - manages database transaction. 


**Managing Database**

- CREATE DATABASE *Database Name* - creates a new database 
- DROP DATABASE *Database Name* - deletes a database and all data in it i.e rows, columns etc


Hello




