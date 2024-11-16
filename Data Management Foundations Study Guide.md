

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
- ALTER TABLE - adds deletes or modifies columns on an existing table




| ALTER TABLE CLAUSE| DESCRIPTION| SYNTAX|
| :-----| :----:| ---:|
| ADD| Adds Column| ALTER TABLE *TableName* ADD *ColumnName* *DataType* ; |
| CHANGE| Modifies Column| ALTER TABLE *TableName* CHANGE *CurrentColumnName* *NewColumnName* *NewDataType* ; |
|Drop| Deletes A column| ALTER TABLE *TableName* DROP *ColumnName* ; |


## Tables

Tables, Columns and rows
All data in relational database is structured in tables

- Table - has a name, fixed sequence of columns and a varying set of rows
- Column - has name and data type
- Row - unnamed sequence of values, each value corresponds to a column and belongs the the columns data type
- Cell - is a single column of a single row


**Rules Governing Tables**

- No Row Order - Rows are not ordered the organization of rows ona. storage device sucha s disk drive never affects query results 


## Data Types

*Data type is a named set of values from which column values are drawn.*


- Integer - Data types represent positive and negative numbers. Several kind exist based on number of bytes needed to allocate for each value
	- INT - implemented as 4 bytes of storage
	- SMALLINT - implemented as 2 bytes of storage 
	  
- DECIMAL stores fractional numeric values, 
	- Decimal - Exact decimal number where M = number of significant digits, D = number of digits after decimal point
	- FLOAT - 4 bytes
	  
- Character - data type represent textual characters
	- VARCHAR - A string of variable length up to specified maximum
	- CHAR - a fixed string of characters
  
- DATE stores year, month and day
	- Date - YYYY-MM-DD. Range: '1000-01-01' - '9999-12-31
	- Time - Format: hh:mm:ss
	- DATETIME - 2/25/2020 10:35:00


#### MySQL Data types

INTEGER 
- TINYINT - 1 byte
- SMALLINT - 2 bytes
- MEDIUMINT - 3 bytes
- INTEGER or INT - 4 bytes
- BIGINT - 8 bytes



## SELECTING ROWS 

#### Operators 
*A symbol that computes a value from one or more values called operands*


| Type | Operator | Description | Example | Value |
|:-|:-:|:-:|:-:|-:|
|Arithmetic| +| adds two numeric values| 4 + 3| 7|
|Arithmetic| - (unary)| reverse the sign of one numeric value| -(-2)|2|
|Arithmetic| - (binary)|subtracts one numeric value from another| 11 - 5|6|
|Arithmetic| * | Multiplies two numeric values| 5 * 3 | 15|
|Arithmetic| / | divides one numeric value by another| 4 / 2| 2|
|Arithmetic| % (modulo)| divides one numeric value by another and returns the integer remainder| 5 % 2| 1|
|Arithmetic| ^| raises one numeric value to the power of another| 5 ^ 2| 25|
|Comparison| =| compares two values for equality| 1 = 2| FALSE|
|Comparison| != |compares two values for inequality| 1 != 2| TRUE|
|Comparison|<| compares two values with <|2 < 2 | FALSE|
|Comparison|<=| compares two values with < = to| 2 <= 2  |TRUE|
|Comparison|>| compares two values with >| 3 > 3| FALSE|
|Comparison|>=|Compares two values with > = |'apple' >= 'Banana'|False|
|Logical|AND|Returns TRUE only when both values are TRUE| TRUE AND FALSE|FALSE|
|Logical|OR|Returns FALSE only when both values are FALSE| TURE OR FALSE|TRUE|
|Logical|NOT| Reverse a logical value| NOT FALSE|TRUE|


## INSERTING, UPDATING, AND DELETING ROWS

#### INSERT
*Adds rows to a table. INSERT statement has two clauses*

- INSERT INTO clause names the table and columns where data to be added. INTO keyword is optional 
- VALUES clause specifies the column values to be added. Values may list any number of rows in parentheses to insert multiple rows
  
```sql
INSERT [INTO] TableName (Column1, Column2, ...) VALUES (Value1, Value2...);
```

#### UPDATE
*Modifies existing rows in the table. Uses the SET clause to specify the new column values*

```sql 
UPDATE PEOPLE SET [name] = 'DREW', [city] = 'NEW YORK CITY' WHERE id = 1;
```

#### DELETE
*Deletes existing Rows in a table The FROM keyword is followed by the table name whose rows are to be deleted*

```sql
DELETE FROM PEOPLE WHERE name = 'DREW';
```

TRUNCATE statement deletes all rows from a table  

```mysql
TRUNCATE TABLE PEOPLE
```

MERGE statement selects data from one table called the source and inserts the data into another table called the target 

## Primary Keys

*A column or group of columns used to identify a row, the primary key is usually the tables first column*

Primary key must be unique and Not NULL

##### SIMPLE PRIMARY KEY
- consists of a single column.
  
##### COMPOSITE PRIMARY KEY
- consists of multiple columns.


#### AUTO INCREMENT COLUMNS 
*A numeric column that is assigned an automatically incrementing value when a new row is inserted* 

- defined by AUTO_INCREMENT keyword which follows the CREATE TABLE statement

*Database users occasionally make the following errors when inserting primary keys*

- Inserting values for auto increment primary keys
- omitting values for primary keys that are not auto increment columns

MySQL allows insertion of a specific value to an auto increment column however overriding auto increment for a primary key is usually a mistake 


## Foreign Keys

*A column or group of columns that refer to a primary key*



#### FOREIGN KEY constraint

*When a **FOREIGN KEY**  constraint is specified the database rejects insert, update and delete statements that violate referential integrity.*


## Referential Integrity

*Referential Integrity* is a relational rule that requires foreign key values are either fully NULL or match some primary key value. 


#### Referential integrity Actions

- **RESTRICT** - rejects an insert, update or delete that violates referential integrity
- **CASCADE** - propagates primary key changes to foreign keys. 


## Constraints 

*A rule that governs allowable values in a database. Constraints are based on relational and business rules*


#### Constraints examples 

- NOT NULL
- DEFAULT
- PRIMARY KEY
- FOREIGN KEY


#### UNIQUE constraint 

*Ensures that the values in a column or group of columns are unique.*

#### CHECK constraint 

*Specifies an expression on one or more columns of a table*

#### Adding and dropping constraints

Constraints are added and dropped with the ALTER TABLE Table name followed by an ADD, DROP or CHANGE clause. 


## Special Operators and Clauses

#### Between operator 

**Between Operator provides an alternative way to determine if a value is between two other values.**

#### Like Operator

**When used in a where cause, Matches text against a pattern using the two wildcard characters % and __**


#### Order BY clause 

**orders selected rows by one or more columns in ascending (alphabetic or increasing order) The DESC keyword with the ORDER BY clause orders rows in descending order.**

### Function

|FUNCTION|DESCRIPTION|EXAMPLE|
|:-|:-:|-:|
|ABS(*n*)|Returns absolute value of *n*|SELECT ABS(-5) returns 5|
|LOWER(s)| returns the lowercase string| SELECT LOWER("MYSQL"); > returns 'mysql'|
|TRIM(s)| Returns the string s without leading and trailing spaces| SELECT TRIM ('           ________test____     '); > returns 'test'|
|HOUR(t), MINUTE(t), SECOND(t)| returns the hour, minuet or second from time t| SELECT HOUR('22:11:45'); returns 22 SELECT MINUTE('22:11:45'); returns 11 SELECT SECOND('22:11:45'); returns 45 |


## AGGREGATE FUNCTIONS 
*Processes values from a set of rows and returns a summary value.*

- COUNT() - counts the number of rows in the set
- MIN() finds the minimum value in the set
- MAX() finds the maximum value in the set
- SUM() finds the all the values in the set
- AVG() computes the arithmetic mean of all the values in a set. 
  
#### Having Clause
*Used with the GROUP BY clause to filter group results*

## Join Queries

*A SELECT statement that combines data from two tables known as the left table and the right table, into a single result. The tables are combined by comparing columns from the left and right tables, usually with the = operator*

*A column name can be replaced with an alias. The alias follows the column name, seperated by an optional AS keyword*


### INNER JOIN and FULL JOINS

- INNER JOIN selects only matching left and right table rows
- FULL JOIN selects all left and right table rows regardless of match. 

### LEFT JOIN and RIGHT JOINS

- LEFT JOIN selects all left table rows but only matching right tbale rows.
- RIGHT JOIN slects all right tbale rows, but only matching left tbale rows. 

*AN outer join is any hjoin that selects unmatched rows, including left, right and full joins* 
*UNION KEYWIORD combines the two results into one table*


#### EQUIJOINS 
*An equijoin compares columns of two tables with the = operator. Most joins are equijoins a NON-EQUIJOIN compares columns with an operator other than = such as < and >*

#### SELF JOINS 
*A self-join joins a table to itself*

#### CROSS JOINS
*Cross joins combine two tables without comparing columns a cross join uses a CROSS JOIN clause without an ON clause.* 


## SUBQUERIES 
*Subquery sometimes called a nested query or inner query is a query within another sql query.*

*Alias is a temporary name assigned to a column or table. The AS keyword follows a column or table name to create an alias*


## COMPLEX QUERY EXAMPLE 

*In some databases view, data can be stored. A materialized view is a view for which data is stored at all times. whenever a base table changes the corresponding view tables can also change, so materialized views must be refreshed. *


#### WITH CHECK OPTION

when with check option is specified the database rejects inserts and updates that do not satisfy the view query WHERE clause. 



## ENTITY RELATIONSHIPS AND ATTRIBUTES 

*high level overview of data requirements ignoring implementation details*



#### ANALYSIS STEPS 

1. discover entities, relationships and attributes
2. Determine cardinality 
3. distinguish strong and weak entities 
4. create supertype and subtype entities

#### LOGICAL DESIGN STEPS

5. implement entities 
6. implement relationships
7. implement attributes 
8. apply normal form 


## CARDINALITY

*refers to maxima and minima of relationships and attributes*

**Relationship maximum** - the greatest number of instances of one entity that can relate to a single instance

**Relationship minimum** - the least number of instances of one entity that can relate to a single instance of another entity. 


*in ER Diagrams, attribute maximum and minimum follow the attribute name. the minimum appears in parentheses*



## SUPERTYPE AND SUBTYPE ENTITIES

*A subtype entity is a subset of another entity type called the supertype entity*


*The identifying relationship is called an IsA relationship*


**Partition** - a group of mutually exclusive subtype entities

#### DATABASE DESIGN 

- After entities relationships attributes cardinality and strong and weak entities are determined the database designer looks for supertype and subtype entities
- Creating supertype and subtypes entities is the last of four analysis steps
- Logical design converts an entity relationship model to tables, columns and keys for a specific database system


## Alternative modeling conventions



















