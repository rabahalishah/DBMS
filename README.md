# DBMS
Data bases are made to store the data. At low level in computers the data is stored in the form of bits and bytes. Lets understand what is data?

## Data
Data is a collection of unorganized, raw material. Data has nothing meaningful or infomative. We have to process the data first to extract the information from it.

Our main goal to make decisions with the data. Data is very valuable like we say "Data is new oil". With the help of data we can extract such information that we can make decisions.

### For example: 
Amazon took feedback on every purchase of their products in the form of rating and information of the buyer. So they can check whether people are liking this particular product or not and which age group is buying and in which season and so on. So that they can take decision for further more production of their product. SO here Amazon is collecting data, processing it, extracting valuable information from it and making best decisions.

# Database
Database is an electronic place where data can be stored, access, managed and update. To make it real use use DBMS

# DBMS
A DBMS is a collection of interrelated data and set of programs (Access, add, update, delete). In simple words DBMS is a software which provide you features like acsess, addition, update and delete and much more customizable queries to play with data in the most convenient and efficient way.

The primary goal of DBMS is to store and retrieve database information in the most efficient and convenient way.

## What is data redundancy in database?
Data redundancy is when multiple copies of the same information are stored in more than one place at a time.

## Why use DBMS? Not file system?
In early time file system were used. But it is very hard to scale and maintain them.

1. Data Redundancy and inconsistency: (e.g we are using file system in a bank we had savings accounts only. After 10 years they started offering current account facility. Now a programmer who made a code for savings account will have to create another program for current account as both accounts operate on different logic so here the programmer will store the information of same person in two places This is called data redundancy. It is a very big issue. And if persons a changes his address then he might forget to change it in both places. Here there would be data inconsistency)
2. Difficulty in accessing data: Programmers will have to write programs to access the data. 
3. Data Isolation: In file system, It is very hard to maintain the actions between transactions to prevent the data interference with each other. 
4. Integrity Problem: The integration of new features is very hard in filesystem and hard to ensures the accuracy, completeness, consistency, and validity of an organization's data.
5. Atomicity problem: Atomicity is a property of DBMS with ensures that the set of database operations all occur or none occur. e.g sending and receiving both should be happenend.
6. Concurrent access anomalies: Two different persons access the same data. The data should be maintained. e.g your bank account is accessing by both you and your family.
7. Security problems: Data breaches and low security access.


**NOTE**: All above 7 are adv of DBMS and it doesnt means that we cannot do all above in file system but it is very hard, time taking and a lot of effort is required to write programs for every operations. To solve this problem DBMS was created.

# Three Schema Architecture
Schema means design.
Before understanding 3 schema architeture. First understand 
## what is Abstraction?
Abstraction is basically a method in which we hide certain information from the user and provide only that information with which he is concerned. e.g A driver do not have concerned about the chemical reactions happening in an engine or how power is transmitting from the engine to the wheels. He is just concerned with the driving of the car. Same thing we do in Operating system as windows we are only exposed to the features. How things are storing and processing at physical level we are not concerned with that.

Three Schema Architecture is used in DBMS. The main object is to provide a personalized view for each user.
It has 3 layers:

## Physical level/ Internal Level Schema:
It is the lowest level of abstraction.
It tells how the data is stored in DB. 
Like data structures etc. 
Here we describe physical structure of data in the harddisk. 
It talks about data encryption, data compression and storage allocation etc.
Remember we created schema in natoursAPI app in our code.
Generally while talking about schemas we are referred with physical or internal level schema.

## Logical Level/ Conceptual level Schema:
Here we conceputally defines our data structure in the form of a table. 
Here we provide a generic view to the user. It contains all the information. 
Logical layer do not care how data is stored and which hardware is used etc. 
It is just concerned with the organizing of data and What are the relationship between the data. e.g courses are for students and students apply in courses.
Users at logical level do not aware about physical information of data. Any changes in the physical level will not effect the data representation at logical level. e.g Change the hardware from HDD to SSD will not effect logical level view.


## External Level/ View Level Schema:
This is the highest level of abstraction. Lets understand it with the example: In Amazon we have information about the buy such as name, CNIC, Phone, Address, Likes, dislikes, Product bought, age. And all this information is stored in the database. It doesnt make sense to give all the information all the departmants of amazon. Logistics department do not have concerned with the likes and dislikes of the user. It just have to deliver the product which user has bought. So in abstraction we hide certain information from the user and provide a personalized view. So here at external level. Only some data fields will be showed to the respective department. In this way the user experience will be enhanced and security will be maintained.

External schemas can be multiple for multiple users.

## Instance
The collection of information at particular time or moment in a DB is called DB instance.

Database of a school showing 1028 students enrolled at 12pm will considered as an instance and next day DB shows 1050 students enrolled at 1am will considered as another instance.

## Schema
Schema is design of DB at logical level.
1.  Schemas have attributes such as name, phone number, student ID etc.
2.  Consistency constraints:  here we also defines things such as name cannot be null, primary key cannot be null etc. (Primary keys): Primary key is a unique key which difference someone. 
3.  Relationship between data.

## Data Model:
Data modelling is done at conceptual or logical level. Here we describe our data or you can say we design our database how it will look like. Relationships, data sematics, consistency constraints etc. 
**Types of models**: we have ER model, Relation model, Object oriented model, Object relational data model etc.

# Database Language:
To interact with DB we need a language:
**DDL:** Data definition languages: Using this we define our schemas, model our data, provide conisitency constraints such as data cannot be null, name cannot exceed 50 characters and so on.
**DML:** Data manipulation language: Using this we manipulate our data such as inserting data, updating, deleting, retreiving data.

SQL offers both features of DDL and DML.

### How will you access your database as your program or app is written in host language such as JS, java, C++
Here comes the interface. An interface comes in when two incompatible things are supposed to communicate.

For mongoDB we use Mongoose
For Java we use JDBC ( java database connectivity)
For C/C++ we use ODBC

These interfaces/ libraries converts our code into SQL or NoSQL queries to interact with the respective database.

# DBA (Database Administrator)
DBA is a person who works on at logical level and have control on both data and programs that can access those data e.g DB of statebank will be used by FBR and taxation departments and so on so here DBA is state bank.

Its functions are:
- Schema definition and physical level organization
- Storage structure
- Authorization control
- Routine maintenance such as Periodic backups, security patches, any upgrades

## Database Application Architecture

**Tier 1 or T1 Architecture:**
In this architecture client, sevrer and DB all lies in the same computer

**Tier 2 or T2 Architecture:**
In this architecture Client sends queries to DB at the server. Security is compromised. DB can be data corrupted if user sent such Queries. you can implement it where very high security is not required and users are not too much

**Tier 3 or T3 Architecture:**
In this architecture client send request to application server and then application server send requests to DB.

This architecture is used by big tech companies where there is big data and it imporves the scalability, security and data integrity. Helps in managing multiple servers. It is used in www servers.

# ER-model
Entity Relationship Model

**Entity:** Entity is a thing or object in the real world that is distinguishable from all other objects and have some properties. It is represented by a square
## Types of entities:
we have two types of entities either 
1. strong (can be strongly distinguished and will have primary key such as student) 
2. weak (may depend on some other entity such as payment. In case of loan, Payment will be exist when we have took a loan. we cannot uniquely identify them). It is represented by a concurrent double square.

### For example:
Each Student in a college is an entity.
Entity Set: It is a set of entities that have same properties or attributes. Student is an entity set cause students in a class will have same properties like everyone will have name, reg,  DOB etc.

## Attributes
Attributes are the properties of Entities.
Student will be entity and its name, reg no., DOB, batch will be its attributes.

Attributes can have consistency constraints such as name characters limit etc.

## Types of Attributes:
**Simple:** Attributes which cannot be further divide or catergorize such as registration number, CNIC number or Bank ID
**Composites:** That can be distribute such as address can be divided into street, ZIP code country, city etc. This helps us to access data by any particular attribute.
**Single value:** Attributes having only single value such as student ID etc.
**Multi-valued:** Attributes have more than one value such as a person can have more than 2 phone numbers.
**Derived:** These are derived from some value such as if you know Date of birth of a person you can calculate its age.
**Null:** This means that the attribute do not have any value or value doesnt exist or the value will be in future.

## Relationship
In ER-Model we make a diagram which represents the relation of attributes with the entities and all have different symbols. Such as dervied attributes will be represented by dotted ellipse, multi-valued attribute willl be represented by double ellipse and composites attribute will have branches.

### Example:
Customer is an entity
customer--> name --> First, middle, last name (composite attribute)
customer--> Customer ID (simple attribute, single value)
customer--> Phone number (multi-value)
customer--> DOB (single value)
customer--> age (derived)
customer--> address --> street --> Street name, street no. (composite)
		    --> City
		    --> state
        	    --> Zip Code

A relationship is defined by a dimond shape.
**For example:** There are two entities such as Customer, loan so the relationship between them is borrow.

Customer borrow loan

### Types of Relation:
**Strong Relation:** Relation between strong entities is called storng relation e.g. Relation between Customer and order will be strong relation as cutomer and order both can have unique IDs
**Weak Relation:** Relation between weak entities is called weak Relation. Loan and payment are weak relation as payment is dependent on loan.

### Degree of relationship:
1. **Uninary Relationship:** One entity participate e.g Manager and employees
2. **Binary relationship:** (commonly used): Two entities will participate e.g Student takes course, customer borrow loans.
3. **Ternary Relationship:** Three entities will participate e.g Employes works in a bank branch and do their Job here we have three entities (Employees, branch, Job) and one relation that is work.


### Relationship Constraints: Mapping Cardinality/ Cardinality Ratio
There will be four steps that we are gonna follow to model our data
1. Different types of relationships between data
2. Referencing/Noramalization vs. Embedding/Denormalization
3. Embedding or Referencing other docuements
4. Types of referencing

The way we design or model our data can make or break our application. Lets discuss the above four mentioned points one by one:

following are different types of relationship constraints or mapping cardinality ratios:

1 : 1 Relation: Movie--> name (One movie can have only one name)
1 : Many: There are three sub types:
	1 : Few: Here a movie can have few awards. A movies cannot have thousands awards. So movie and awards will have 1: few relation.
	1 : Many: Here movie can have thousands of reviews. So movie and review will have 1:Many relation 
	1 : Ton: An App can have ton of logs. here it is hard to differentiate between Many and Ton. You can simply take it as a thing which approaches to infinity can be catergories as `	1 : Ton Relation. As an app can have infinite logs. so it is a 1:Ton Relation. The diff. between Many and Ton will help us in selecting whether we are supposed to normalize or 	denormalize the data
Many : 1: Movies and actors: 10 movies can be cast 1 hero actor.
Many:Many: There are several actors in a movie. On the same side an Actor can work in a several movies. So this would be catergories as Many:Many Relationship

## Participation constraints
**Customer and loan:** Partial participation (In customer entity set there can be some customers who did not have taken any loan and some have taken the loan)
**Loan and customer:** Total participation (In loan entity set all loans will must have a customer. It is not possible that the loan has issued but there is no owner) it is represented by double lines

## Extended ER-Features: Specialization
In specialization we use the concept of inheritance in which there is parent class and then we create children classes. All children classes will also have attributes of their parent class.
By definition Specialization is basically a splitting of entities into the group of sub-entities on the basis of their functionalities and specialization. It is a top-down approach.

## Why we need specialization feature? 
The answer is to avoid redundancy. Reduncy means the repeatition of same information at different places. And make our Database blueprint more refined.
**For example:**
A person is a parent class having attributes such as name and address then I create an instance of this class as customer and employees
customer will have customer ID, Profile pic, memership. Employee will have role and salary

now these two instances will be connected to the person parent class as "Is a" relation.
Person is a customer
person is an employee

here customer and employee both have name and address inherite in them.

Here in this way we can add more specialization and easily scale our database.
such as we can inherite more classes namely Developers, HR, Managers with Employee class. Now Developer, HR, Manager all will have attributes of employee and person. 

**NOTE**: By specialization we have categorized each entity group. And each sub-entity group contains only necessary information. Its not like that customer also have salary which doesnt make sense. It allow developers to extract relevant information for sub-entity group

**Other examples:**
Engineer entities can have sub-entities of civil, mechanical and electrical.

Vehicles can have sub-entities of car, buses and trucks and so on. Here there will be some common properties which will be add with the parent entity so it will automatically get inherited with cars, buses, and trucks. and same for the engineer example.


## Generalization
It is the reverse of Specialization. We go from bottom to top in generalization.
Actually Generlization and Specialization both end up with the same diagram. There is nothing much difference both are simply the way of thinking. 

let say we you made an entitiy vehicle and then it have sub-entities such as bus, car and truck. Then you noticed that bus, car and truck all have 2 more common properties so instead of adding these common properties you add them in the parent class/entity Vehicle so that these common attributes will automatically get inherit in the sub-entities.

**The reason why need to do generalization is same as of doing specialization. (The answer is to avoid redundancy. Reduncy means the repeatition of same information at different places. And make our Database blueprint more refined.)**

**NOTE:** Inheritance happens in both generalization and specialization.

## Participation Inheritance.
If Parent entitiy is involved in some relation then its child entity will automatically get involved in that relation.

## Aggregation
How to show relationship among relationships?
Aggration is the technique 

## How to formulate ER-Diagram?
Steps to follow to make ER-Diagram:
1. Identify Entity Set
2. Identify Attributes and their types
3. Identify the relationships between them entities and constraits (Cardinality mapping and their pariticipation)


## Example of ER-Model of a Bank
First we will identify Entity Sets and their types:

**Entity Sets:**
Branch (Strong entity),
Customer (Strong entity), 
Employee (Strong entity), 
saving A/C, 
current A/C, (For saving and current a/c we can use generalization or specializaiton as they will have common attributes)
Loan, 
payment (Weak entity)

**Attributes:**
Branch: name (primary-key), city, assets, liablities.
Customer: Customer-Id (primary-key), name, address (composite), contact-no (multi-valued), DOB (singl valued), age (derived) 
Employee: emp-id (primary-key), contact-no (multi-valued), dependant-name (composite), year of service (derived), start-date (single-valued)
Saving-accounts: interest-rate, daily with-drawl, acc-no, balance
Current-account: Transaction charges, overdraft amount, acc-no, balance (here acc-no and balance both are common in saving and current a/c so we do not repeat them instead we will use generalzation)
Loan: loan-number, amount
Weak-entity: payment no., date, amount

**Relationship**
Cutomer Borrows loan: N:N
loan orginated by branch N:1
loan-payment 1:N
Customer deposit account N:N
Cutomer banker employe N:1
Employee manage by Employe
N:1

# Relational Model
Relaitonal model is very similar to ER model but in this model we reperesent our data in the form of tables. My entities will be the columns and rows will be the each entry which we called tuple.

## Degree of table:
Means No of attributes or we can say number of columns
**cardinalities:** In relational model number of rows/tuple are my cardinalities.

Whenever a DB is designed we first create ER model and then we convert ER-model diagram to relational Model. 
We convert our entities into the tables and their attributes into the columns for those tables. And for relationship between these entities we use foreign keys

Then with the help of RDBMS--> Relational Database management system (RDMS consists of collection of tables and each table will have unique name)
It is a software used for the implementation of Relational model.
We use MySQl, Oracle, etc.

Properties of tables in RDBMS:
1. The name of Relation must be distinguished from the other.
2. The values should be atomic (cannot be divided further).
3. The name of each attribute/column must be unique.
4. Each tuple must be unique in table
5. The sequence of rows and columns doesnt matter.
6. Table must follows the integrity constraints -it helps to maintaint data consistency accross the tables.


## Types of keys
- **Super key (SK):** Any permutation or combination of attributes that can uniquely identify the tuple can be a super key. e.g Combination of name and customer ID. It can be null.
- **Candidate Key (CK):** Subset of super key. There should not be any redundancy. e.g in case of {name, customer ID} super key we can have {customerID} as candidate key. (people can have same names that why it has been excluded to avoid redudancy). It cannot be null.
- **Primary Key (PK):** Selected from the candidate key set. and has least number of attributes. It cannot be Null.
- **Alternate Key:** All CK except PK
- **Foreign Key (FK):** A key which is a primary key of some other table used to define the relation is called Foreign key. For example we have two tables Customer (Customer_Id, name, address, contact-no) and order (order_id, time_stamp, delivery date) here to define the "places" relation between them we will add another attribute in order table which will be 		  the customer Id that is a primary key of customer table. so now, order table (order_id, time_stamp, delivery date, Customer_Id). Now Customer table will be called as 		  parent/referenced table as its primary key has been used and order table will be called as child/referencing table as it is using the foreign key. 

**FOREIGN KEY CAN HAVE NULL VALUE:** On delete null. When we delete value from parent table then in child table we put null value of foreign key. and this will not violate delete constraints rule.
**Surrogate Key:** Let say you have data of two schools now you wanna merge them. But the problem is that both schools have different format for their registeration number. So we cannot use them as primary or unique key so we ask system to generate a key and assign it. This key is called Surrogate key. It is nothing simply integer.

## Constraints
SQL Constraints
SQL constraints are used to specify rules for the data in a table.

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.

**The following constraints are commonly used in SQL:**

NOT NULL - Ensures that a column cannot have a NULL value
UNIQUE - Ensures that all values in a column are different
PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
FOREIGN KEY - Prevents actions that would destroy links between tables
CHECK - Ensures that the values in a column satisfies a specific condition
DEFAULT - Sets a default value for a column if no value is specified
CREATE INDEX - Used to create and retrieve data from the database very quickly

### Integrity constraints
RDBMS supports integrity constraints to avoid data inconsistency such as pre-defining the data types of attributes.

### Referential Constraints:
**Insert Constraints:** We cannot insert tuple in the child table if its corresponding value is not in the parent table.
**Delete constraints:** We cannot delete tuple from the parent table if value corresponding to it is in the childe table.

**If you want to delete a value from parent table without violating the delete constraint then you have to delete its corresponding value from the child table also. using On delete cascade.**

### Not Null Constraint
We defines that the value of particular attribute cannot be null

### Unique Constraint
We define certain attribute to be unique so that they do not repeat them self such as Registration number.

### Default Constraint
Here we define a default value if user didn't provide a value to the attribute.

### Check Constraint
This constraints limit the domains of the attribute such as age<=80 etc.

### Primary Key Constraint
here we define any attribute a our primary key such as ID

### Foreign key Constraint
Whenever there is a relationship between two entities then there must be something common between them. This common attribute must be a primary key an entity set and will act as the foreign key of other entity set. This key will prevent actions that can result in loss of connection between the tables.

# SQL
SQL stands for structured query language. We use SQL to perform CRUD operations on Data to RDBMS. MySQL is itself an RDBMS which allows us to perform CRUD operation on data using SQL.

# Install and setting up MySQL

First of all install below applications for your respective operating systems:
> MySQL Community server
> MySQL community bench (UI for creating Schemas, Relations of in short designing DB)

> Adding MySQL to Path windows enviromental variables

- Go to: C:\Program Files\MySQL\MySQL Server 8.3\bin

- Open the Start Search, type “env” or “environment variables,” and click on “Edit the system environment variables.”

- In the System Properties window, click on the “Environment Variables…” button.

- In the Environment Variables window, under the "System variables" section, find and select the "Path" variable.
Click on “Edit…”.

- In the Edit Environment Variable window, click “New” and paste the path to your MySQL bin directory.
- Click “OK” on all open windows to save your changes.

- Open a new Command Prompt window.
Type
```mysql --version
```
 to verify that MySQL is recognized

# Starting MySQL server using CLI
(make sure you have added MySQL in to you windows env variable path)
```bash
>mysql -u root -p
```
(Enter your password and you will be connected)

# Quick Start

```
CREATE DATABASE any_name;
(This command is used to create Database)
```
```
USE your_database_name;
(this command is used to switched to the existing DB)
```
```
CREATE TABLE student(id INT PRIMARY KEY, name VARCHAR(225));
(This command is used to create a table namely student having two attributes along with their defined data types)
```

```bash
INSERT INTO student VALUES(2,'Rabah Ali Shah');
(This command is used to insert values in the table)
```

```bash
SELECT * FROM student;
This command is used to filter and display the selected data. * means all
```
```bash
DROP DATABASE IF EXISTS database_name;
(This command is used to delete database)
```

## SQL Data Types:
The data types are used to define the type and domain (length) of an attribute. SQL provides several datatypes. Just google SQL Datatypes and see the table.

## Difference Between VARCHAR and CHAR
Both are used to defined characters but CHAR allocate the fixed space in the memory no matter smaller bit character is storing in it. It will carry the fixed space. But VARCHAR will vary its size in the memory according to the word coming.

# Types of SQL commands
### DDL (Data Definition Language):
```
1. CREATE: this query syntax is used to create table in SQL
Syntax: CREATE TABLE table_name (column_1 datatype, column_2 datatype, column_3 datatype);
```
```
2. ALTER TABLE: this query is used to add column in your existing table
Syntax: ALTER TABLE table_name ADD column_name datatype;
```
```
3. DROP: delete table, DB, view, query to delete whole table.
Syntax: DROP TABLE table_name;
```
```
4. TRUNCATE: remove all the tuples from the table.
```
```
5. RENAME: Used to Remane the Tables
Syntax: ALTER TABLE table_name RENAME COLUMN old_name to new_name;
```

### DML (data modification language)
1. INSERT: insert data into a relation, (this query is used to enter data/tuples in the table)

```
Syntax: INSERT INTO table_name (column_1, column_2, column_3) VALUES ('Value_1', 'Value_2', 'Value_3'); 
Shorthand syntax: INSERT INTO table_name VALUES ('Value_1', 'Value_2', 'Value_3');
Syntax: INSERT INTO users (name,age,birthday) VALUES ('john',12,2003-01-09);
````

2. UPDATE: update relation data.

```Syntax: UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;```
> ON UPDATE CASCADE
**NOTE: Can be added to the table while creating constraints. Suppose there is a situation where we have two tables
such that primary key of one table is the foreign key for another table. if we update the primary key of the first
table then using the ON UPDATE CASCADE foreign key of the second table automatically get updated.

3. DELETE: delete row(s) from the relation.
```Syntax: DELETE FROM table_name WHERE condition;```

**Question: What would happen to child entry if parent table’s entry is deleted?**
**Answer:** You will get an error but to overcome it we will > DELETE CASCADE - (to overcome DELETE constraint of Referential constraints). On deleting the Pk in the parent table the FK in the child table will be automatically get deleted.

Where as If you will use ON DELETE NULL then On deleting the Pk in the parent table the FK in the child table will be automatically get converted to NULL.

**Syntax of DELETE CASCADE:**
```
>CREATE TABLE ORDER (
order_id int PRIMARY KEY,
delivery_date DATE,
cust_id INT,
CodeHelp

FOREIGN KEY(cust_id) REFERENCES customer(id) ON DELETE CASCADE
);
```

**Synatx of ON DELETE NULL:**
```
ON DELETE NULL - (can FK have null values?)
CREATE TABLE ORDER (
order_id int PRIMARY KEY,
delivery_date DATE,
cust_id INT,
FOREIGN KEY(cust_id) REFERENCES customer(id) ON DELETE SET NULL
);
```


### DCL (Data Control language): grant or revoke authorities from user.
1. GRANT: access privileges to the DB
2. REVOKE: revoke user access privileges.

### TCL (Transaction control language): to manage transactions done in the DB
1. START TRANSACTION: begin a transaction
2. COMMIT: apply all the changes and end transaction
3. ROLLBACK: discard changes and end transaction
4. SAVEPOINT: checkout within the group of transactions in which to rollback.

### MANAGING DB (DDL):
Creation of DB:
1. CREATE DATABASE IF NOT EXISTS db-name;
2. USE your_database_name; //need to execute to choose on which DB CREATE TABLE etc commands will be executed.
//make switching between DBs possible.
3. DROP DATABASE IF EXISTS your_database_name; //dropping database.
4. SHOW DATABASES; //list all the DBs in the server.
5. SHOW TABLES; //list tables in the selected DB.

### DRL/DQL (Data Retrieval Language):
1. Syntax: SELECT <set of column names> FROM <table_name>;
2. Order of execution of a command in SQL is from RIGHT to LEFT.

**Question: Can we use SELECT keyword without using FROM clause?**

1. Yes, using DUAL Tables.
2. Dual tables are dummy tables created by MySQL, help users to do certain obvious actions without referring to user defined tables.
3. e.g., SELECT 55 + 11; // this will give the answer 66 but that answer will be shown in a tuple of a table. And that table will be a dummy table created by MySQL cuz MySql always show data in tables.

** DRL (cont.):**

**WHERE command:**
```Syntax: UPDATE table_name SET column_name = some_value WHERE column_name = some_value```
// query to is used to update or make changes in your existing table.
```E.g., SELECT * FROM customer WHERE age > 18;```

**AND Command:**
```SELECT * FROM customer WHERE age between 0 AND 100;```
In the above e.g., 0 and 100 are inclusive.

**IN**
```SELECT * FROM officers WHERE officer_name IN ('Lakshay', ‘Maharana Pratap', ‘Deepika’);```

**AND/OR/NOT**
1. AND: WHERE cond1 AND cond2
2. OR: WHERE cond1 OR cond2
3. NOT: WHERE col_name NOT IN (1,2,3,4);

**IS NULL**
SELECT * FROM customer WHERE prime_status is NULL;

### Pattern Searching / Wildcard (‘%’, ‘_’) OR Regex:
here ‘%’, any number of character from 0 to n. Similar to ‘*’ asterisk in regex.
here  ‘_’, only one character.
example: ```SELECT * FROM customer WHERE name LIKE ‘%p_’; //in output the second last word will be "p"```

*******ORDER BY
Sorting the data retrieved using WHERE clause.
```> ORDER BY <column-name> DESC;```
here DESC = Descending and ASC = Ascending
```e.g., SELECT * FROM customer ORDER BY name DESC;```

### GROUP BY

GROUP BY Clause is used to collect data from multiple records and group the result by one or more column. It is
generally used in a SELECT statement.
Groups into category based on column given.

```> SELECT c1, c2, c3 FROM sample_table WHERE condition GROUP BY c1, c2, c3.```

All the column names mentioned after SELECT statement shall be repeated/written again after GROUP BY, in order to successfully execute the query.

### Aggreagation Functions:
Used with aggregation functions to perform various actions.
1. COUNT()
2. SUM()
3. AVG()
4. MIN()
5. MAX()


### DISTINCT
Find distinct values in the table. (Distinct means that let say you want to find how many job positions are there in a company and you have a data set. You think that you will use SELECT command on Job Positions and you will get the desired result. In actual you will get a complete column where are the job positions will be written. Some job titles will be repeated. You do not want whole job positions list. You just want to know how many job positions are there such as developer, hr etc. SO using distinct with SELECT clause will help you in finding the desired result)
```
> SELECT DISTINCT(col_name) FROM table_name;
```

GROUP BY can also be used for the same
```> SELECT col_name FROM table GROUP BY col_name; same output as above DISTINCT query.```

**SQL is smart enough to realise that if you are using GROUP BY and not using any aggregation function, then you mean “DISTINCT”.**


### GROUP BY HAVING
Out of the categories made by GROUP BY, we would like to know only particular thing (cond). Similar to WHERE.
```> Select COUNT(cust_id),country FROM customer GROUP BY country HAVING COUNT(cust_id) > 50;```


### Difference between WHERE and HAVING
1. Both have same function of filtering the row base on certain conditions.
2. WHERE clause is used to filter the rows from the table based on specified condition
3. HAVING clause is used to filter the rows from the groups based on the specified condition.
4. HAVING is used after GROUP BY while WHERE is used before GROUP BY clause.
5. If you are using HAVING, GROUP BY is necessary.
6. WHERE can be used with SELECT, UPDATE & DELETE keywords while GROUP BY used with SELECT.


### DDL Constraints:
**Primary Key:**
Primary is a unique key, used to differentiate a table.
Primary key cannot be null, it must be unique. its a good practice to make primary key of INT (integer) data type.

**Foreign Key:**
Foreign key as its name suggest its a key in a table that is coming from another table. FK refers to PK of other table.
Each relation can have any number of FK.
```
CREATE TABLE ORDER (
id INT PRIMARY KEY,
delivery_date DATE,
order_placed_date DATE,
cust_id INT,
FOREIGN KEY (cust_id) REFERENCES customer(id)
);
```

The table which is using the FK is called child table/ referencing table. And the table of which PK is used as FK is called parent /referenced table.

**UNIQUE constraint:**
1. Unique, can be null, table can have multiple unique attributes.

```
CREATE TABLE customer (
email VARCHAR(1024) UNIQUE,
);
```

**CHECK constraints**
checks are implemented while defining our schema model. To allow values which are fulfilling the condition such as domain/length of characters etc.
```
CREATE TABLE customer (
...
CONSTRAINT age_check CHECK (age > 12),
...
);
```

2. “age_check”, can also avoid this, MySQL generates name of constraint automatically.

**DEFAULT**
This constraint is used to set default value of an attribute if its value is not provided.

```
>CREATE TABLE account (

saving-rate DOUBLE NOT NULL DEFAULT 4.25, //now in case, user will not provide the value of saving-rate attribute then automatically 4.25 value will assigned to the attribute.

);
```

**Note:** An attribute can have PK and FK both in a table.


**REPLACE**
Mainly used for already present tuple in a table.

It Will work as As UPDATE, using REPLACE with the help of WHERE clause in PK, then that row will be replaced.
It will work As INSERT, if there is no duplicate data new tuple will be inserted.
```
> REPLACE INTO student (id, class) VALUES(4, 3);
> REPLACE INTO table SET col1 = val1, col2 = val2;
```

### JOINING

#### JOINING TABLES
All RDBMS are relational in nature, we refer to other tables to get meaningful outcomes.
FK are used to do reference to other table.

#### INNER JOIN
Returns a resultant table that has matching values from both the tables or all the tables.
```
>SELECT column-list FROM table1 INNER JOIN table2 ON condition1;

>INNER JOIN table3 ON condition2
```

**Alias in MySQL (AS)**
1. Aliases in MySQL is used to give a temporary name to a table or a column in a table for the purpose of a particular query. It works as a nickname for expressing the tables or column names. It makes the query short and neat.
```
> SELECT col_name AS alias_name FROM table_name;
> SELECT col_name1, col_name2,... FROM table_name AS alias_name;
```

**OUTER JOIN**
**LEFT JOIN**
This returns a resulting table that takes all the data from left table and the matched data from the right table.
SELECT columns FROM table LEFT JOIN table2 ON Join_Condition;

**RIGHT JOIN**
This returns a resulting table that all the data from right table and the matched data from the left table.
SELECT columns FROM table RIGHT JOIN table2 ON join_cond;

**FULL JOIN**
This returns a resulting table that contains all data when there is a match on left or right table data.
Emulated (means there is no direct/built-in command) in MySQL. We have to create this by using LEFT and RIGHT JOIN.
```
> LEFT JOIN UNION RIGHT JOIN.
> SELECT columns FROM table1 as t1 LEFT JOIN table2 as t2 ON t1.id = t2.id
UNION
SELECT columns FROM table1 as t1 RIGHT JOIN table2 as t2 ON t1.id = t2.id;
```
**NOTE:** UNION ALL, can also be used this will duplicate values as well while UNION gives unique values.

**CROSS JOIN**
This returns all the cartesian/combinations products of the data present in both tables. Hence, all possible variations are reflected in the output. Used rarely in practical purpose.
Table-1 has 10 rows and table-2 has 5, then resultant would have 50 rows.
```>SELECT column-lists FROM table1 CROSS JOIN table2;```

**SELF JOIN**
A SELF JOIN for a given table is a join that performs between two identical copies of that table. Used very less. Emulated using INNER JOIN.
``` SELECT columns FROM table as t1 INNER JOIN table as t2 ON t1.id = t2.id;```

**SET Operations**
Row wise combination. Comines table vertically. Datatypes of the corresponding columns from each table should be the same. It generate distinct rows. Combination is a resulting set from two or more select statement.
**UNION**
Combines two or more SELECT statements.
```
>SELECT * FROM table1
UNION
SELECT * FROM table2;
```

Number of column, order of column must be same for table1 and table2.
**INTERSECT**
Returns common values of the tables. Emulated.
```
> SELECT DISTINCT column-list FROM table-1 INNER JOIN table-2 USING(join_cond);
> SELECT DISTINCT * FROM table1 INNER JOIN table2 ON USING(id);
```

**MINUS**
This operator returns the distinct row from the first table that does not occur in the second table. Emulated.
```
> SELECT column_list FROM table1 LEFT JOIN table2 ON condition WHERE table2.column_name IS NULL;
> e.g., SELECT id FROM table-1 LEFT JOIN table-2 USING(id) WHERE table-2.id IS NULL;
```

### Sub-Queries
Its basically a concept of dividing tasks into small task.
Outer query depends on inner query.
Alternative to joins.
Nested queries.
```
>Syntax: SELECT column_list (s) FROM table_name WHERE column_name OPERATOR
(SELECT column_list (s) FROM table_name [WHERE]);
> e.g., SELECT * FROM table1 WHERE col1 IN (SELECT col1 FROM table1);
Sub queries exist mainly in 3 clauses
```
Inside a WHERE clause.
Inside a FROM clause.
Inside a SELECT clause.


**Subquery using FROM clause**
```
> SELECT MAX(rating) FROM (SELECT * FROM movie WHERE country = ‘India’) as temp;
```

**Subquery using SELECT**
```
SELECT (SELECT column_list(s) FROM T_name WHERE condition), columnList(s) FROM T2_name WHERE
condition;
```

**Derived Subquery**
```SELECT columnLists(s) FROM (SELECT columnLists(s) FROM table_name WHERE [condition]) as new_table_name;```

**Co-related sub-queries (like a loop)**
With a normal nested subquery, the inner SELECT query
runs first and executes once, returning values to be used by
the main query. A correlated subquery, however, executes
once for each candidate row considered by the outer query.
In other words, the inner query is driven by the outer query.


**JOIN vs Sub-queries**
**JOINs are:**
- faster
- it put maximum calculation burden on RDBMS
- it is complex, difficult to implement

**Sub-queries are:**
- slower
- put max calculation burden on user
- easier to implement

**MySQL VIEW:**
Views can be understand by the concept of higher level abstraction. In views we provide or show only necessary data of the table/schemas about which the user is concern other information is keep hidden from the user.
Below as some syntax of creating, deleting and modifying the views.
```
> CREATE VIEW view_name AS SELECT columns FROM tables [WHERE conditions];
> ALTER VIEW view_name AS SELECT columns FROM table WHERE conditions;
> DROP VIEW IF EXISTS view_name;
> CREATE VIEW Trainer AS SELECT c.course_name, c.trainer, t.email FROM courses c, contact t WHERE c.id = t.id; (View
using Join clause).
```

**COMMENTS in SQL**
**Multi line comment:**

/*SELECT * FROM Customers;
SELECT * FROM Products;
SELECT * FROM Orders;
SELECT * FROM Categories;*/

****Single Line Comment
--Happy Comment

**BACKUP DATABASE**
```
> BACKUP DATABASE databasename TO DISK = 'filepath';
> BACKUP DATABASE testDB TO DISK = 'D:\backups\testDB.bak';
> BACKUP DATABASE databasename TO DISK = 'filepath' WITH DIFFERENTIAL;
A differential back up only backs up the parts of the database that have changed since the last full database backup.
```

**Changing the DATATYPE**
>ALTER TABLE table_name ALTER COLUMN column_name datatype;

## How to disable safe mode in MySQL:
```
SET SQL_SAFE_UPDATES = 0;
```
when safe mode is ON then actions such as deleting table will not be executed.

**What is a Stored Procedure?**
A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.
So if you have an SQL query that you write over and over again, save it as a stored procedure, and then just call it to execute it.
You can also pass parameters to a stored procedure, so that the stored procedure can act based on the parameter value(s) that is passed.

Stored Procedure Syntax:
```
>CREATE PROCEDURE procedure_name
AS
sql_statement
GO;	

>EXEC procedure_name;
```

# Normalization in DBMS
## What is normalisation?
normalisation is an optimzation technique to optimise the DB and reduce redundancy (Data redundancy is when multiple copies of the same information are stored in more than one place at a time.)

# Functional dependency:
Its simply a relation. That one attribute is dependant on other. means that one attribute can be determined by the other attribute. Its a relation between primary key (or set of primary key) or other attributes which are dependent on them

A-->B means that A can be used to find B or B can be determined by using A. Here A is determinant and B is Dependent.

## Types of Functional Dependencies:
### Trivial FD (Obvious):
It states that A-->B if B is dependent on A so must be the subset of A. 

e.g A{1, 2, 3} and B{1,2}  A-->B true

### Non-Trivial:
Opposite of Trivial. Here A-->B is true but B is not a subset of A

### Rules of FD:
### Reflexive:
Same as Trivial
A-->B is true where B is a subset of A

### Augmentation:
If A-->B true then Augmentation of any other attribute such as C on both side will also be true: AC-->BC

### Transitivity:
If A-->B and B-->C then A-->C

### Why Normalizatoin?
To avoid data redundancy in DBMS.

### What if we have redundant data in our DB?
If we will have redundant data in our database then we will have to face data inconsistency and 3 anomalies/abnormalities:

### Insertion Anomaly:
Let say we have a database table having columns/Attributes such as (id, name, age, branch code, branch name, branch HoD).
(First of all you may have noticed that branch information and student information both are different entities and must be in separate table. But lets take this example for leanring purpose)
Let say a new student came and he has not assigned with the branch of the school. So you cannot insert information in the DB as you dont have branch info. Despite both are independant. And here name of branch and branch HoD will be keep repeating their information. In case HoD gets changed then you have to change the information of HoD each and everywhere. Which leads to data redundancy. This is an example of insertion anomaly that either you can put information due to the other and you have to change information everywhere.

### Deletion Anomaly:
Lets take the above example again. Now this time imagine all students of mechanical engineering departments get graduated. Now there names should be removed from the DB. But if you will remove their names then all information of mechanical dept branch will also get removed which will leads to show that ME dept do not exists in the DB which is not right. This is Deletion anomaly that important information can be removed due to redundancany of data.

### Updation Anomaly:
In case branch gets a new HoD, then you have to change the information of HoD each and everywhere in the database. Which leads to data redundancy. This is an example of updation anomaly that you have to change information everywhere.

## Normalisation role:
Now we can say Normalization helps in prevention of above mentioned anomalies.
Normalization divides the composite attributes into individual attributes or larger tables into smaller tables and link them using relations.

**We will keep on dividing the tables until we achieve SRP.....Single Responsibility Principle (means each table must take responsibility of single entity/Information/Idea)**

### Types of normal forms:
**1NF (NF = Normal Form):**
There must be atomic attribute (which cannot be further divided).
There should not be multi-valued attributes.

**2NF:**
Relation must be 1NF
There should not be any partial dependency.
(complete dependency: All non-prime attributes must be fully dependent on Primary Key
Partial dependancy: All non-prime attributes do not completely dependent on the part of primary key (this happens when your primary key is a combination of two attributes))

**3NF:**
Relation must be 2NF
Transitivity shoud not exist. (A-->B, B-->C, then A-->C this is transitivity. Which also leads to data redundancy.)

**BCNF (Boye-codd normal form):**
Relation must be 3NF.
A-->B here B here should be primary key, A must be a super key. (Primary key should not be determined by any non-primary attribute)


## Advantages of Normalization
- Helps to minimise data redundancy
- Greater overall database organization
- Data consistency maintains.


# Transactions in DBMS
**Transaction: "Money can neither be created nor be destroyed but it can transfer from one account to another"**
Transactions are basically set of instruction which have either two states of execution. Either successful or failed. There is nothing in between.
For transactions sender and receiver both are considered as a single system.
For a layman trasaction is basically a single step process. BUt in actual therea are several steps in between.

Let say there is system in which we have two accounts. Account A sender and Account B receiver. Account A have 2000 balance and he sends 500 ruppee to Account B who have 3000 balance. Total balance in the system is 5000. After transaction A should have 1500 and B should have 3500. Total again 5000.

This will happen in following steps:
read(A);
A=A-500;
wirte(A);
read(B);
B=B+500;
wirte(B);

but all these 6 steps would be count as single steps. Any one of the steps get failed. Transaction would be failed.

There are some properties of a transaction which must be followed which are called ACID properties:

**ACID Properties of Transaction**
1) **Atomicity:** This means that all transaction processes will be count as single process. Or you can say all operations related to transaction in the DB will be process or none will be processed.
2) **Consistency:** Integrity constraint must be maintained before and after transaction OR you can say total amount in the system will be remain same before and after transaction.
3) **Isolation:** When multiple transactions are happening. Then one transaction will not have any idea about other transaction.
4) **Durability:** After transaction completes successfully, the changes it has made to the database persist, even if there are system failures.


### States of Transaction: Behind the scenes of transaction
when a transaction is being made then the all the changes are being made in a buffer memory. After that the changes are committed into the actual database. In case of failure the previous state will be restored.

Its a journey from active state to terminated state
At active state R/W operations are being made in case of any failure in R/W operation the transaction will be stop immedeiately and system will be move to failed state in case of successfull R/W operations, system will be moved to partially terminated state. Here again system fails at partially terminiated state it will sent to failed state and from there to abort state otherwise it will be send to fully committed state and then to terminated state to successfully complete the transaction process.


**Active state**
The very first state of the life cycle of the transaction, all the read and write operations are being performed. If they execute without any error the T comes to Partially committed state. Although if any error occurs then it leads to a Failed state.

**Partially committed state**
After transaction is executed the changes are saved in the buffer in the main memory. If the changes made are permanent on the DB then the state will transfer to the committed state and if there is any failure, the T will go to Failed state.

**Committed state**
When updates are made permanent on the DB. Then the T is said to be in the committed state. Rollback
can’t be done from the committed states. New consistent state is achieved at this stage.

**Failed state**
When T is being executed and some failure occurs. Due to this it is impossible to continue the execution of the T.

**Aborted state**
When T reaches the failed state, all the changes made in the buffer are reversed. After that the T rollback completely. T reaches abort state after rollback. DB’s state prior to the T is achieved.

**Terminated state**
A transaction is said to have terminated if has either committed or aborted.

### How to implement Atomicity and Durability (How DB will handle in case of process get failed):
There are some methods which we implement to achive atomitity and durability which are given below:

### Shadow Copy Scheme:
**Brief:** In this method a pointer is being used. That pointer is pointing toward the un-updated/ old DB copy then we create a copy of that DB and perform actions on it. Once the operations are successfully done on that copy we make that the pointer will point toward the updated DB and old DB will be deleted and transaction will be successful. Copying, reading, updating and changing the pointer all considered as single process. This is how we deal with atomicity. And in case of any failure the new DB copy will be deleted and pointer will not be changed as it was pointing toward the old DB and it will keep pointing toward the old DB. This is how we deal with durability.

**Explanation:**
1. Based on making copies of DB (aka, shadow copies).
2. Assumption only one Transaction (T) is active at a time.
3. A pointer called db-pointer is maintained on the disk; which at any instant points to current copy of DB.
4. T, that wants to update DB first creates a complete copy of DB.
5. All further updates are done on new DB copy leaving the original copy (shadow copy) untouched.
6. If at any point the T has to be aborted the system deletes the new copy. And the old copy is not affected.
7. If T success, it is committed as,
1. OS makes sure all the pages of the new copy of DB written on the disk.
2. DB system updates the db-pointer to point to the new copy of DB.
3. New copy is now the current copy of DB.
4. The old copy is deleted.
5. The T is said to have been COMMITTED at the point where the updated db-pointer is written to disk.
8. Atomicity
1. If T fails at any time before db-pointer is updated, the old content of DB are not affected.
2. T abort can be done by just deleting the new copy of DB.
3. Hence, either all updates are reflected or none.
9. Durability
1. Suppose, system fails are any time before the updated db-pointer is written to disk.
2. When the system restarts, it will read db-pointer & will thus, see the original content of DB and none of the effects of T will
be visible.
3. T is assumed to be successful only when db-pointer is updated.
4. If system fails after db-pointer has been updated. Before that all the pages of the new copy were written to disk. Hence,
when system restarts, it will read new DB copy.
10. The implementation is dependent on write to the db-pointer being atomic. Luckily, disk system provide atomic updates to entire
block or at least a disk sector. So, we make sure db-pointer lies entirely in a single sector. By storing db-pointer at the beginning
of a block.
11. Inefficient, as entire DB is copied for every Transaction.

### Log based recovery method
**Brief:** In this method we deffered (delay) the transaction process by creating logs side by side. We do not perfrom trasactions we just create log of each process and then once the process get successfully executed we execute the logs and complete the transaction. In case of any failure we refers to the logs and re-take actions accordingly.

sample logs in deferred method:
Ti means any transaction
A means account A, 950 means new value
<Ti, start>
<Ti, A, 950>
<Ti, B, 2050>
<Ti, Commit>

**Explanation:**
1. The log is a sequence of records. Log of each transaction is maintained in some stable storage so that if any failure occurs, then it can be recovered from there.
2. If any operation is performed on the database, then it will be recorded in the log.
3. But the process of storing the logs should be done before the actual transaction is applied in the database.
4. Stable storage is a classification of computer data storage technology that guarantees atomicity for any given write operation
and allows software to be written that is robust against some hardware and power failures.


**Deferred DB Modifications**

1. Ensuring atomicity by recording all the DB modifications in the log but deferring the execution of all the write operations
until the final action of the T has been executed.
2. Log information is used to execute deferred writes when T is completed.
3. If system crashed before the T completes, or if T is aborted, the information in the logs are ignored.
4. If T completes, the records associated to it in the log file are used in executing the deferred writes.
5. If failure occur while this updating is taking place, we preform redo.


**Immediate DB Modifications**
Sample log:
<Ti, start>
<Ti, A, 1000, 950>
<Ti, B, 2000, 2050>
<Ti, Commit>

here 1000 is old value, 950 is new
1. DB modifications to be output to the DB while the T is still in active state.
2. DB modifications written by active T are called uncommitted modifications.
3. In the event of crash or T failure, system uses old value field of the log records to restore modified values.
4. Update takes place only after log records in a stable storage.
5. Failure handling
1. System failure before T completes, or if T aborted, then old value field is used to undo the T.
2. If T completes and system crashes, then new value field is used to redo T having commit logs in the logs.

**Check points**
A CHECKPOINT is a process that writes all the dirty pages (modified data pages) from memory to the disk. This operation is essential for performance and recovery purposes.
During a CHECKPOINT, the transaction log records the information about the completed transactions, and the dirty pages are written to the data files on disk.

In the event of a system failure or database restore, SQL Server uses the transaction log to bring the database back to a consistent state.
The combination of regular CHECKPOINT operations and the transaction log allows SQL Server to recover the database to a point just before the failure, minimizing data loss.
When a transaction is committed, the corresponding changes in the transaction log are marked as "committed," indicating that the changes are now permanent.

# Indexing in DBMS:
Index is an optional technique which is applied on large data to optimize the data access. It is used to locate the data in the table quickly. It exactly like an index table on the start of a book. You just see the topic and page number directly go to that page. If there was no index at the start of the book then you had to go through the whole book to search the desired topic. 

There are two things in our index table:
-  **Search Key:** Contains copy of primary key or candidate key
		of the table or something else.
- **Data Reference:** Pointer holding the address of disk block
		where the value of the corresponding key is stored.

**Index file is always stored in Memory for fast access.**

# Indexing Methods
## Primary Indexing (Clustering or sorted):
Primary indexing goal is to have a list which must be sorted on the basis of any key/attribute. Data must be sorted. As we can apply binary search on sorted data which is very fast. If data will not be sorted we will have to use linear searching which is very slow. 

In indexing we will give indexes to data in the list. In index list there will be a search key and for each search key there will be a corresponding pointer which will pointing toward the address of the block in the disk. We will apply binary search on index table and then on getting the specified block in the disk we will again apply binary index on the block to get the desired data point inside the block.

There are two further concepts in Indexing:
1) **Dense Indexing:**
	In dense indexing we assign index to each value of the data. It requires more space. As all entries will be in the dense index table.

2) **Sparse Indexing:**
	In this indexing only some of the blocks are assigned with indexes.

**You can apply index on two types of basis:**
**Based on Key attributes:**
Data file will be stored w.r.t primary key attribute. Primary key will be used as search key in the index table. No. of entries = No. of blocks in datafile. It is an example of sparse indexing.

**Based on non-key attributes:**
Data file will be stored w.r.t non-primary key attribute. Remember non-primary key can repeat itself so we have to give index to each unique value of non-primary key attribute. So, No. of entries = No. of unique keys in non-primary attributes in datafile. It is an example of Dense Indexing as we are giving indexing to all unique attributes in the datafile.

**Multi-lvl indexing:**
Index with two or more levels. Here index table is further have its index table. This is used where the data is very very large.
If the single level index become enough large that the binary search it self would take much time, we can break down indexing into multiple levels.

## Secondary Index (Non-Clustering Index)
Here Datafile is unsorted. Hence, Primary Indexing is not possible. Here we assign index corresponding to each entry which is sorted. Then we apply binary search on search key we have made ourself and which is sorted. Can be done on key or non-key attribute. Called secondary indexing because normally one indexing is already applied. No. Of entries in the index file = no. of records in the data file. It's an example of Dense index.


**Advantages of Indexing**
1. Faster access and retrieval of data.
2. IO is less.

**Limitations of Indexing**
1. Additional space to store index table
2. Indexing Decrease performance in INSERT, DELETE, and UPDATE query.

# NoSQl database:
NoSQL means "Not only SQL" This means that this database is something more than SQL. Yes, its true. Shortly, The main purpose to introduce this database was scalabilty irrespective of the data redundancy. In NoSQL databases there is data redundancy but the data scalability is easier and data retrieval is very fast. It was built to deal with unstructured data. 
NoSQL databases (aka "not only SQL") are non-tabular databases and store data differently than relational tables. NoSQL databases
come in a variety of types based on their data model. The main types are document, key-value, wide-column, and graph. They
provide flexible schemas and scale easily with large amounts of data and high user loads.
1. They are schema free.
2. Data structures used are not tabular, they are more flexible, has the ability to adjust dynamically.
3. Can handle huge amount of data (big data).
4. Most of the NoSQL are open source and has the capability of horizontal scaling.
5. It just stores data in some format other than relational.


## History behind NoSQL
1. NoSQL databases emerged in the late 2000s as the cost of storage dramatically decreased. Gone were the days of needing to create a complex, difficult-to-manage data model in order to avoid data duplication. Developers (rather than storage) were becoming the primary cost of software development, so NoSQL databases optimised for developer productivity.
2. Data becoming unstructured more, hence structuring (defining schema in advance) them had becoming costly.
3. NoSQL databases allow developers to store huge amounts of unstructured data, giving them a lot of flexibility.
4. Recognising the need to rapidly adapt to changing requirements in a software system. Developers needed the ability to iterate quickly and make changes throughout their software stack — all the way down to the database. NoSQL databases gave them this flexibility.
5. Cloud computing also rose in popularity, and developers began using public clouds to host their applications and data. They wanted the ability to distribute data across multiple servers and regions to make their applications resilient, to scale out instead of scale up, and to intelligently geo-place their data. Some NoSQL databases like MongoDB provide these capabilities.

**NoSQL Databases Advantages**

A) **Flexible Schema:** RDBMS has pre-defined schema, which become an issue when we do not have all the data with us or we need to change the schema. It's a huge task to change schema on the go.
B) **Horizontal Scaling:** Horizontal scaling, also known as scale-out, refers to bringing on additional nodes/PCs/Servers to share the load. This is difficult with relational databases due to the difficulty in spreading out related data across nodes. As in SQL we mostly apply joining methods so in case of several PCs we have to first gather the data via 		network to one single node then we will apply joining methods and joining methods will take further processing which makes scaling-out impractical on SQL Relation models. Whereas, With non-relational databases, this is made simpler since collections are self-contained and not coupled relationally. This allows them to be distributed across nodes more simply, as queries do not have to “join” them together across nodes. Scaling horizontally is achieved through Sharding OR Replica-	sets.
C) **High Availability:** NoSQL databases are highly available due to its auto replication feature i.e. whenever any kind of failure happens data replicates itself to the preceding consistent state. If a server fails, we can access that data from another server as well, as in NoSQL database data is stored at multiple servers.
D) **Easy insert and read operations:** Queries in NoSQL databases can be faster than SQL databases. Why? Data in SQL databases is typically normalised, so queries for a single object or entity require you to join data from multiple tables. As your tables grow in size, the joins can become expensive. However, data in NoSQL databases is typically stored in a way that is optimised for queries. The rule of thumb when you use MongoDB is data that is accessed together should be stored together. Queries typically do not require joins, so the queries are very fast. But difficult delete or update operations.
E) Caching mechanism.
F) NoSQL use case is more for Cloud applications

# When to use NoSQL?
1. Fast-paced Agile development
2. Storage of structured and semi-structured data
3. Huge volumes of data
4. Requirements for scale-out architecture
5. Modern application paradigms like micro-services and real-time streaming.
6. Where Data redundancy is not an issue.

## Misconceptions about NoSQL DB 
1) **Relationship data is best suited for relational databases:**
	A common misconception is that NoSQL databases or non-relational databases don’t store relationship data well. NoSQL databases can store relationship data — they just store it 	differently than relational databases do. In fact, when compared with relational databases, many find modelling relationship data in NoSQL databases to be easier than in relational 	databases, because related data doesn’t have to be split between tables. NoSQL data models allow related data to be nested within a single data structure.

2) **NoSQL databases don't support ACID transactions:** Another common misconception is that NoSQL databases don't support ACID transactions. Some NoSQL databases like MongoDB do, in fact, 	support ACID transactions.


## Types of NoSQL Data Models
1) **Key-Value Stores:**
1. The simplest type of NoSQL database is a key-value store. Every data element in the database is stored as a key value pair
	consisting of an attribute name (or "key") and a value. In a sense, a key-value store is like a relational database with only
	two columns: the key or attribute name (such as "state") and the value (such as "Alaska").
2. Use cases include shopping carts, user preferences, and user profiles.
3. e.g., Oracle NoSQL, Amazon DynamoDB, MongoDB also supports Key-Value store, Redis.
4. A key-value database associates a value (which can be anything from a number or simple string to a complex object) with
	a key, which is used to keep track of the object. In its simplest form, a key-value store is like a dictionary/array/map object
	as it exists in most programming paradigms, but which is stored in a persistent way and managed by a Database
	Management System (DBMS).
5. Key-value databases use compact, efficient index structures to be able to quickly and reliably locate a value by its key,
	making them ideal for systems that need to be able to find and retrieve data in constant time.
6. There are several use-cases where choosing a key value store approach is an optimal solution:
	a) Real time random data access, e.g., user session attributes in an online application such as gaming or finance.
	b) Caching mechanism for frequently accessed data or configuration based on keys.
	c) Application is designed on simple key-based queries.

2) **Column-Oriented / Columnar / C-Store / Wide-Column:**
1. The data is stored such that each row of a column will be next to other rows from that same column.
2. While a relational database stores data in rows and reads data row by row, a column store is organised as a set of columns. This means that when you want to run analytics on a small 	number of columns, you can read those columns directly without consuming memory with the unwanted data. Columns are often of the same type and benefit from more efficient 	compression, making reads even faster. Columnar databases can quickly aggregate the value of a given column (adding up the total sales for the year, for example). Use cases include 	analytics.
3. e.g., Apaceh Cassandra, RedShift and ScyllaDB.

3) **Document Based Stores:**
1. This DB store data in documents similar to JSON (JavaScript Object Notation) objects. Each document contains pairs of fields and values. The values can typically be a variety of types 	including things like strings, numbers, booleans, arrays, or objects.
2. Use cases include e-commerce platforms, trading platforms, and mobile app development across industries.
3. Supports ACID properties hence, suitable for Transactions.
4. e.g., MongoDB, CouchDB.

4) **Graph Based Stores:**
1. A graph database focuses on the relationship between data elements. Each element is stored as a node (such as a person in a social media graph). The connections between elements are 	called links or relationships. In a graph database, connections are first-class elements of the database, stored directly. In relational databases, links are implied, using data to 	express the relationships.
2. A graph database is optimised to capture and search the connections between data elements, overcoming the overhead associated with JOINing multiple tables in SQL.
3. Very few real-world business systems can survive solely on graph queries. As a result graph databases are usually run alongside other more traditional databases.
4. Use cases include fraud detection, social networks, and knowledge graphs.

# NoSQL Databases Dis-advantages
1) **Data Redundancy:**
Since data models in NoSQL databases are typically optimised for queries and not for reducing data duplication, NoSQL databases can be larger than SQL databases. Storage is 	currently so cheap that most consider this a minor drawback, and some NoSQL databases also support compression to reduce the storage footprint.
2) Update & Delete operations are costly.
3) All type of NoSQL Data model doesn’t fulfil all of your application needs:
	1. Depending on the NoSQL database type you select, you may not be able to achieve all of your use cases in a single database. For example, graph databases are excellent for 	analysing relationships in your data but may not provide what you need for everyday retrieval of the data such as range queries. When selecting a NoSQL database, consider what your 	use cases will be and if a general purpose database like MongoDB would be a better option.
4) Doesn’t support ACID properties in general.
5) Doesn’t support data entry with consistency constraints.


# SQL vs NoSQL
**Data Storage Model:** In SQL we have, Tables with fixed rows and columns. Whereas, In NoSQL DB, Document: JSON documents, Key-value: key-value pairs, Wide-column: tables with rows and
			dynamic columns, Graph: nodes and edges.
**Development History:** SQL was Developed in the 1970s with a focus on reducing data duplication. Whereas NoSQl, Developed in the late 2000s with a focus on scaling and allowing for rapid application change driven by agile and DevOps practices.
**Examples:** **For SQL:** Oracle, MySQL, Microsoft SQL Server, and PostgreSQL. **For NoSQL:** Document: MongoDB and CouchDB, Key-value: Redis and DynamoDB, Wide-column: Cassandra and HBase, Graph: Neo4j and Amazon Neptune
**Primary Purpose:** SQL is for General Purpose. It can be used in any case except where horizontal scalling is required. It doesnt means that you cannot do horizontal scaling (using 	disributed PCs/Server) you can, but it is not practicle in case of SQL relational DB which makes them not good for clouds. Whereas NoSQL is general purpose, Key-value: large amounts of data with simple lookup queries, Wide-column: large amounts of data with predictable query patterns, Graph: analyzing and traversing relationships between connected data.
**Schemas:** SQL have fixed schemas, Whereas NoSQL have Flexible.
**Scaling:** SQL allows Vertical (Scale-up). Whereas NoSQL allows Horizonatal (Scale-out accross commodity servers)
**ACID Properties:** SQL supports ACID Properties, whereas NoSQL do not support ACID properties except DB like MongoDB. 
**JOINS:** JOINS are Typically required in JOINS. Whereas in NoSQL joins are typically not allowed.
**Data to Object Mapping:** SQL Required object-relational mapping, whereas NoSQL Many do not require ORMs. MongoDB documents map directly to data structures in most popular programming 	languages.


# Referencing/Noramalization vs. Embedding/Denormalization in NoSQL databases.
In Referecning or Normalization we keep our data separated and well organized. We always add references of chiled object in parent objects object. 
For exmaple:
Abstraction is applied to treat relationships as higher level entities. 

For example:
we have a "work on" relationship between job, employe and branch.

we want to add an entity manager which will manage all of them. so here we will consider relationship between job, employe and branch as single higher level entity and then will its relation with manager entity as "manages" relation.
Now we can read this relation as 

Manager manages "relationship between job, employe and branch"
```
//Movie Name
{
  "_id": ObjectID('222'),
  "title": "Intersteller",
  "releaseYear": '2014',
  "actors":[
    ObjectID('555'),
    ObjectID('666'),
    ObjectID('777'),

  ]
}
//Actor 1
{
  "_id": ObjectID('555'),
  "name": "Matthew Mc",
  "age": '50',
  "born":"Uvale, USA"
}
//Actor 2
{
  "_id": ObjectID('666'),
  "name": "Andriedue",
  "age": '26',
  "born":"LA, USA"
}
//Actor 3
{
  "_id": ObjectID('777'),
  "name": "Anne Hathaway",
  "age": '37',
  "born":"NYC, USA"
}
```

//Here Moview Name object is a parent object which conatains all the IDs of actors.
#### PROS and CONS :
1. Its easier to query each document on its own
2. we need more than one query to get data from the refered object

**In Embedding or denoramilzation all the data is embedded in the parent object. It is not separated as above.**
**For example:**
```
{
  "_id": ObjectID('222'),
  "title": "Intersteller",
  "releaseYear": '2014',
  "actors":[
    //Actor 1
    { 
      "name": "Matthew Mc",
      "age": '50',
      "born":"Uvale, USA"
    },
    //Actor 2
    { 
      "name": "Andriedue",
      "age": '26',
      "born":"LA, USA"
    },
    //Actor 3
    {
      "name": "Anne Hathaway",
      "age": '37',
      "born":"NYC, USA"
    }

  ]
}
```

// here you can see the actors and movie both are in the same object:

#### PROS and CONS of denormalizing in NoSQL
1. Performance: We get all the information in one query.
2. Impossible to query the embedded document on its own.


### How to decide when to embedd/de-normalize and when to reference/normalize the data?
There are few factors on which we determine whether the data should be normalize or de-normalize. The decision would not be made on the basis of any factor in isolation. The decision would be made in combination.
There is NO HARD RULE to decide in which form the data should be sturctured.

Relationship Type:                 Embedded/De-normaliztion: 1: FEW 		Referencing/Normalization: 1:Many
(How two datasets are 					     1: Many					    1:Ton
related to each other)											    Many:Many

### For example:

We have a two dataset: Movies + Images (100) Here it is a 1:Many Relationship. Here since the images are not too much. So therefore, we can simply embed or de-normalize the data.

Data Access Pattern:                 Embedded/De-normaliztion: Data is mostly Read 		Referrencing/Normalization: Data is updated a lot
(How often data is read  				       Data doesn't change quickly			            (low Read/write Ratio)
and write: Read/Write Ratio)				       (High Read/write Ratio)				

### For example:
If there is a dataset of Movies + Images then in this case the images and movies are only read there is no way to update the image. So in this case simply embedd the data is suitable. Whereas if there is a dataset of Movies + Reviews then we can normalize/referrencing the data as reviews can be updated a lot. 

Data Closeness:                 Embedded/De-normaliztion: Dataset really belong together 		Referrencing/Normalization: We frequently need to query both datasets on their own.
(How much data is  					     					    
related. How we want											    
to query)

**For example:**
If there is a datasets of user+ email address then in this case it is suitable to have emails embedded in users object. Whereas if there is a data set such as movies + images then in this case we should go for normalization. As there is case in which user have to tell the name of a movie on the basis of the image shown to him. Then here we are querying two datasets on their own so normalizing/referecing the data would be more suitable. 

**NOTE:** There is max 16MB limit on Document in mongoDB we cannot exceed this limit. So remember this limitation while modeling your data.

## Types of Referencing/Normalization
Once we have let say decided to Normalize our data then we still have to go through to select one out of three types of referencing.
### Child Referencing:
```
{
  "_id": ObjectID('222'),
  "title": "Intersteller",
  "releaseYear": '2014',
  "actors":[
    ObjectID('555'),
    ObjectID('666'),
    ObjectID('777'),

  ]
}
//Actor 1
{
  "_id": ObjectID('555'),
  "name": "Matthew Mc",
  "age": '50',
  "born":"Uvale, USA"
}
//Actor 2
{
  "_id": ObjectID('666'),
  "name": "Andriedue",
  "age": '26',
  "born":"LA, USA"
}
//Actor 3
{
  "_id": ObjectID('777'),
  "name": "Anne Hathaway",
  "age": '37',
  "born":"NYC, USA"
}
```
// Here this type of referecing is called child Referencing. This type of referencing is only suitable for 1: FEW relationship type. The reason is that as you can see in parent array of Movies the actor array can be long long enough as if there would be so many actors and as we all know in MongoDB each object is count as each document which size should not exceed  16MB. But in case of soo many actors the actors array would be large enough to make the size of this document/obj to exceed 16MB. So therefore, this child refercing is suitable for 1:FEW relationship where its child array have few child elements.

## Parent Referencing:
```
//parent
{
  "_id": ObjectID('23'),
  "app": "My Movie Database",

}

//children
{
  "_id": ObjectID('1'),
  "app": ObjectID('23'),
  "type": 'error',
  "timestamp": 23453287432
}

{
  "_id": ObjectID('2'),
  "app": ObjectID('23'),
  "type": 'error',
  "timestamp": 23453287432
}
```

//Here  you can see every child remember his parent by their IDs but parents have no idea about their children. This case very suitable for 1:Many and 1: Ton relationship type. As there is no fear of exceeding 16MB for each document.

**Two-way Referencing:**
```
{
  "_id": ObjectID('23'),
  "title": "Intersteller",
  "releaseYear": '2014',
  "actors":[
    ObjectID('555'),
    ObjectID('666'),
    ObjectID('777'),
    //and many more...

  ]
}

//Actor 1
{
  "_id": ObjectID('555'),
  "name": "Matthew Mc",
  "age": '50',
  "born":"Uvale, USA",
  "movies":[
	ObjectID('23'),
        //and many more
]
}

//Actor 2
{
  "_id": ObjectID('666'),
  "name": "Andriedue",
  "age": '26',
  "born":"LA, USA",
  "movies":[
	ObjectID('23'),
        //and many more
]
}
//Actor 3
{
  "_id": ObjectID('777'),
  "name": "Anne Hathaway",
  "age": '37',
  "born":"NYC, USA",
  "movies":[
	ObjectID('23'),
        //and many more
]
}

```
// Here in this case both the parents and childs are referecing each other. cause An actor can work in several movies and A movie can have several actors. So this type of referencing is best for many-many relation.


### Summary
1. Sturcture youe data the way your application queries and updates data.
2. Identify the question arises from the application use case first and then model your data. So that the questions can get answered in the most efficient way.
3. In general, always favor embedding/De-normalizing, unless there is a good reason for normalizing it. Especially for 1:FEW and 1:Many relationships.
4. A 1:Ton and MANY:MANY relationships are usually the good reason to go for normalizing the data.
5. favor referecning when the data is updated alot and if you need to access a dataset on its own.
6. Use embed/denormalization when the data is mostly read but rarely updated.
7. Do not allow arrays to grow indefinitely. Therefore if you need to normalize, use Child referencing for 1:Few or 1:Many relationship and use Parent referencing for 1:Ton relationships.
8. Use two way referencing for Many:Many Relationship.


# Types of DB
Following are some major types of DB
### Relation DB:
1. Based on Relational Model.
2. Relational databases are quite popular, even though it was a system designed in the 1970s. Also known as relational database
management systems (RDBMS), relational databases commonly use Structured Query Language (SQL) for operations such as
creating, reading, updating, and deleting data. Relational databases store information in discrete tables, which can be JOINed
together by fields known as foreign keys. For example, you might have a User table which contains information about all your
users, and join it to a Purchases table, which contains information about all the purchases they’ve made. MySQL, Microsoft SQL
Server, and Oracle are types of relational databases.
3. they are ubiquitous, having acquired a steady user base since the 1970s
4. they are highly optimised for working with structured data.
5. they provide a stronger guarantee of data normalisation
6. they use a well-known querying language through SQL
7. Scalability issues (Horizontal Scaling).
8. Data become huge, system become more complex.

## OOD (object oriented DB):
This DB works on the OOP concepts in which we implement Abstraction, encapusaltion, inheritence, polymorphism. 
In OOP we know we have classes and these classes have instance which we called objects. 
**Classes have attributes** (which tells their characteristics) and **methods/functions** (which tells their behavior).
The object-oriented data model, is based on the object-oriented-programming paradigm, which is now in wide use.
Inheritance, object-identity, and encapsulation (information hiding), with methods to provide an interface to objects, are among the key concepts of object-oriented programming that have found applications in data modelling. The object-oriented data model also supports a rich type system, including structured and collection types. While inheritance and, to some extent, complex types are also present in the E-R model, encapsulation and object-identity distinguish the object-oriented data model from the E-R model.
2. Sometimes the database can be very complex, having multiple relations. So, maintaining a relationship between them can be
tedious at times.
1. In Object-oriented databases data is treated as an object.
2. All bits of information come in one instantly available object package instead of multiple tables.
**Advantages**
1. Data storage and retrieval is easy and quick.
2. Can handle complex data relations and more variety of data types that standard relational databases.
3. Relatively friendly to model the advance real world problems
4. Works with functionality of OOPs and Object Oriented languages.

**Disadvantages**
1. High complexity causes performance issues like read, write, update and delete operations are slowed down.
2. Not much of a community support as isn’t widely adopted as relational databases.
3. Does not support views like relational databases.
5. e.g., ObjectDB, GemStone etc.

**NoSQL DB:**
1. NoSQL databases (aka "not only SQL") are non-tabular databases and store data differently than relational tables. NoSQL
databases come in a variety of types based on their data model. The main types are document, key-value, wide-column, and
graph. They provide flexible schemas and scale easily with large amounts of data and high user loads.
2. They are schema free.
3. Data structures used are not tabular, they are more flexible, has the ability to adjust dynamically.
4. Can handle huge amount of data (big data).
5. Most of the NoSQL are open sources and has the capability of horizontal scaling.
6. It just stores data in some format other than relational.

**Hirarchical DB:**
As the name suggests, the hierarchical database model is most appropriate for use cases in which the main focus of information
gathering is based on a concrete hierarchy, such as several individual employees reporting to a single department at a
company.
2. The schema for hierarchical databases is defined by its tree-like organisation, in which there is typically a root “parent”
directory of data stored as records that links to various other subdirectory branches, and each subdirectory branch, or child
record, may link to various other subdirectory branches.
3. The hierarchical database structure dictates that, while a parent record can have several child records, each child record can only
have one parent record. Data within records is stored in the form of fields, and each field can only contain one value. Retrieving
hierarchical data from a hierarchical database architecture requires traversing the entire tree, starting at the root node.
4. Since the disk storage system is also inherently a hierarchical structure, these models can also be used as physical models.
5. The key advantage of a hierarchical database is its ease of use. The one-to-many organisation of data makes traversing the
database simple and fast, which is ideal for use cases such as website drop-down menus or computer folders in systems like


Microsoft Windows OS. Due to the separation of the tables from physical storage structures, information can easily be added or
deleted without affecting the entirety of the database. And most major programming languages offer functionality for reading
tree structure databases.
6. The major disadvantage of hierarchical databases is their inflexible nature. The one-to-many structure is not ideal for complex
structures as it cannot describe relationships in which each child node has multiple parents nodes. Also the tree-like
organisation of data requires top-to-bottom sequential searching, which is time consuming, and requires repetitive storage of
data in multiple different entities, which can be redundant.
7. e.g., IBM IMS.

**Network DB:**
Extension of Hierarchical databases
2. The child records are given the freedom to associate with multiple parent records.
3. Organised in a Graph structure.
4. Can handle complex relations.
5. Maintenance is tedious.
6. M:N links may cause slow retrieval.
7. Not much web community support.
8. e.g., Integrated Data Store (IDS), IDMS (Integrated Database Management System),
Raima Database Manager, TurboIMAGE etc.


# Clustering in DBMS
Its is one the most important DBMS concept as it is widely used today in cloud based products. Clustering is basically a replication of Databases. Instead of using single server of large bandwidth for handling DBMS request all over the world. We multiple servers and all servers have same data inside it. By doing this requests will be divided that will save bandwidth cost, increase availablity of data, easy maintainance, load balancing. 

**Detail:**
Database Clustering (making Replica-sets) is the process of combining more than one servers or instances connecting a single database.
Sometimes one server may not be adequate to manage the amount of data or the number of requests, that is when a Data Cluster is needed.
Database clustering, SQL server clustering, and SQL clustering are closely associated with SQL is the language used to manage the database
information. Replicate the same dataset on different servers.
## Advantages
1) **Data Redundancy:** Clustering of databases helps with data redundancy, as we store the same data at multiple servers. Don’t confuse this
data redundancy as repetition of the same data that might lead to some anomalies. The redundancy that clustering offers is required and is
quite certain due to the synchronisation. In case any of the servers had to face a failure due to any possible reason, the data is available at other
servers to access.
2) **Load balancing:** or scalability doesn’t come by default with the database. It has to be brought by clustering regularly. It also depends on the
setup. Basically, what load balancing does is allocating the workload among the different servers that are part of the cluster. This indicates that
more users can be supported and if for some reasons if a huge spike in the traffic appears, there is a higher assurance that it will be able to
support the new traffic. One machine is not going to get all of the hits. This can provide scaling seamlessly as required. This links directly to
high availability. Without load balancing, a particular machine could get overworked and traffic would slow down, leading to decrement of
the traffic to zero.
3) **High availability:** When you can access a database, it implies that it is available. High availability refers the amount of time a database is
considered available. The amount of availability you need greatly depends on the number of transactions you are running on your database
and how often you are running any kind of analytics on your data. With database clustering, we can reach extremely high levels of availability
due to load balancing and have extra machines. In case a server got shut down the database will, however, be available.
4) **How does Clustering Work?**
In cluster architecture, all requests are split with many computers so that an individual user request is executed and produced by a number of
computer systems. The clustering is serviceable definitely by the ability of load balancing and high-availability. If one node collapses, the
request is handled by another node. Consequently, there are few or no possibilities of absolute system failures.


# CDN
There is same concept called CDN (Content delivery Network or content distribution network)
A content delivery network, or content distribution network (CDN), is a geographically distributed network of proxy servers and their data centers. The goal is to provide high availability and performance by distributing the service spatially relative to end users. CDNs came into existence in the late 1990s as a means for alleviating the performance bottlenecks of the Internet as the Internet was starting to become a mission-critical medium for people and enterprises. Since then, CDNs have grown to serve a large portion of the Internet content today, including web objects (text, graphics and scripts), downloadable objects (media files, software, documents), applications (e-commerce, portals), live streaming media, on-demand streaming media, and social media sites.

CDNs are a layer in the internet ecosystem. Content owners such as media companies and e-commerce vendors pay CDN operators to deliver their content to their end users. In turn, a CDN pays Internet service providers (ISPs), carriers, and network operators for hosting its servers in their data centers.

**How CDN works?**
CDN nodes are usually deployed in multiple locations, often over multiple Internet backbones. Benefits include reducing bandwidth costs, improving page load times, and increasing the global availability of content. The number of nodes and servers making up a CDN varies, depending on the architecture, some reaching thousands of nodes with tens of thousands of servers on many remote points of presence (PoPs). Others build a global network and have a small number of geographical PoPs.

Requests for content are typically algorithmically directed to nodes that are optimal in some way. When optimizing for performance, locations that are best for serving content to the user may be chosen. This may be measured by choosing locations that are the fewest hops, the lowest number of network seconds away from the requesting client, or the highest availability in terms of server performance (both current and historical), to optimize delivery across local networks. When optimizing for cost, locations that are the least expensive may be chosen instead. In an optimal scenario, these two goals tend to align, as edge servers that are close to the end user at the edge of the network may have an advantage in performance or cost.

# Partitioning in DBMS
It is same as clustering but the difference is that in partitioning replication is not happen. We actually divide and then distribute our data in more than one server. To manage the load, requests coming. 

If you will have big data in your single server then your server will get exhausted.

**Detail:**
1. A big problem can be solved easily when it is chopped into several smaller sub-problems. That is what the partitioning technique does. It divides a
big database containing data metrics and indexes into smaller and handy slices of data called partitions. The partitioned tables are directly used by
SQL queries without any alteration. Once the database is partitioned, the data definition language can easily work on the smaller partitioned slices,
instead of handling the giant database altogether. This is how partitioning cuts down the problems in managing large database tables.
2. Partitioning is the technique used to divide stored database objects into separate servers. Due to this, there is an increase in performance,
controllability of the data. We can manage huge chunks of data optimally. When we horizontally scale our machines/servers, we know that it gives us
a challenging time dealing with relational databases as it’s quite tough to maintain the relations. But if we apply partitioning to the database that is
already scaled out i.e. equipped with multiple servers, we can partition our database among those servers and handle the big data easily.

### Vertical Partitioning
1. Slicing relation vertically / column-wise.
2. Need to access different servers to get complete tuples.
4. Horizontal Partitioning
1. Slicing relation horizontally / row-wise.
2. Independent chunks of data tuples are stored in different servers.

**When Partitioning is Applied?**
1. Dataset become much huge that managing and dealing with it become a tedious task.
2. The number of requests are enough larger that the single DB server access is taking huge time and hence the system’s response time become
high.

### Advantages of Partitioning
1. Parallelism (managing and sending the requests to the respective server coming from the end user)
2. Availability
3. Performance
4. Manageability
5. Reduce Cost, as scaling-up or vertical scaling might be costly.


### Distributed Database
1. A single logical database that is, spread across multiple locations (servers) and logically interconnected by network.
2. This is the product of applying DB optimisation techniques like Clustering, Partitioning and Sharding.
3. Why this is needed? READ Point 5.

## Sharding
1. Technique to implement Horizontal Partitioning.
2. The fundamental idea of Sharding is the idea that instead of having all the data sit on one DB instance, we split it up and introduce a
Routing layer so that we can forward the request to the right instances that actually contain the data.

### Pros
1. Scalability
2. Availability

### Cons
1. Complexity, making partition mapping, Routing layer to be implemented in the system, Non-uniformity that creates the necessity of Re-
Sharding

2. Not well suited for Analytical type of queries, as the data is spread across different DB instances. (Scatter-Gather problem)
CodeHelp

**NOTE**: Sharding and partitioning both terms are used in DBMS. But sharding generally refers dividing the data horizontally.


# Scalling Patterns: How databases get scaled practically in industries
In this section we will study a business problem or you can say a case study where a app become famous from its local area to a continent. It will be a cab booking app like UBER. There will be step by step 7 patterns to scale a database and its optimization. You can implement these patterns to any of your project according to your need.

Following are the 7 patterns:
**Pattern 1:** Query Optimization and connection pool implemenation
**Pattern 2:** Vertical Scaling or Scale up
**Pattern 3:** CQRS: Command query responsibilty segregation
**Pattern 4:** Multi primary replication
**Pattern 5:** Partitioning of data by functionality
**Pattern 6:** Horizontal Scalling or Scale out
**Pattern 7:** Data centre wise partition

## Case Study:
Tiny Startup, 10 customers on board....Since there are very small customers at start we can use a single small machine you can say a personal computer which stores, customers, trips, locations, booking data, and customer trip history.
You are getting 1 trip request in 5 mins on average.

Now you app is becoming famous and now the problem begins. Now requests have been increasing from upto 30 requests per minutes. Since your DB is very small its starts getting exhaust and perform poorly. you have noticed that there is problem in API latency that has been increased there is a delay which our users are facing, Transactions facing deadlocks, starvation and frequent failure, sluggish app experience.

### The solution?
1) We will have to apply performance optimization measures.
2) Scale the database


Lets discuss all these patterns in detail:
# 1) Pattern 1: Query Optimization and connection pool implemenation:
a) One thing that you can do is to Cache frequently used non-dynamic data like, booking history, payment history, user profiles etc. The information which will not change you can cache them in the users app storage so that you can improve some data retreiving. For cachse you canUse connection pool libraries to Cache DB connections.
b) You can also Introduce Database Redundancy. (Or may be use NoSQL). I know data redundancy is not good but sometimes it is beneficial. When your databases is highly normalised (less reduncdancy) Then SQL queries will be complex and will require some further join methods to get the desired data. The easiest way is to avoid normalising so that retreival of data can be increased.
c) Whenever you make a connection request you will have to wait. The solution is that you can already built some connection pool so that the connection time can be saved.

Now your app is have Good optimisations 

# 2) Pattern 2: Vertical Scaling or Scale up
Now you planned to Scaled the business to one more city, and now getting ~100 booking per minute.
Now you can improve your system hardware.

a) Upgrading our initial tiny machine. RAM by 2x and SSD by 3x etc. Scale up is pocket friendly till a point only. More you scale up, cost increases exponentially.

Now your have again Good Optimisation as of now.


# Pattern 3: CQRS: Command query responsibilty segregation
Now Business is growing, you decided to scale it to 3 more cities and now getting 300 booking per minute.

Since you are now getting 300 req/min. You server is unable to handle so much request efficiently. So here 
The scaled up big machine is not able to handle all read/write requests. so you decided to buy another machine primiraly for dealing with the write request. Here you will do clustering. One will be primary and other will be secondary for reading requests. Secondary will be replica of primary. Secondary PC will be update its data by looking at primary pc after fixed interval of time so that they could maintain data consistency. Separate read/write operations physical machine wise. 2 more machines as replica to the primary machine. All read queries to replicas. All write queries to primary. Now you have balanced the load.

Now your Business is growing.

# Pattern 4: Multi primary replication

Now your business is growing and you decided to scale it to 2 more cities.
but the problem here is that the Primary PC is not able to handle all write requests as you have scaled your business to 2 more cities
there is a Lag between primary and replica is impacting user experience. (This is the same gap as you may have noticed when you book a ride and your rider's car is showing on the map. The car is not following the route smoothly it is lagging. The reason is data reading latency.)

### Solution:
Why not distribute write request DB to replica also? Yes, here we will buy some more PCs and make them all machines can work as primary & replica. Multi primary configuration is a logical circular ring. The app can Write data to any node. Since all the computers are connected in a ring shape you can Read data from any node that replies to the broadcast first.


# Pattern 5: Partitioning of data by functionality
Now You scale to 5 more cities & your system is in pain again. (~50 req/s)

Here you can create a separate database for some other functions. What about separating the "location tables" in separate DB schema? What about putting that DB in separate machines with primary-replica or multi-primary configuration?

Different DB can host data categorised by different functionality. Backend or application layer has to take responsibility to join the results. You have to write a application layer in the backend.

# Pattern 6: Horizontal Scalling or Scale out
Now, Planning to expand your business to other country. 

Now for scalling you can do Sharding - multiple shards. (Separating data row wise in different machines. Keeping the schemas same in all DBs)

Now you Allocate 50 machines - all having same DB schema - each machine just hold a part of data. Locality of data should be there. Each machine can have their own replicas, may be used in failure recovery. Sharding is generally hard to apply. But “No Pain, No Gain”


# Pattern 7: Data centre wise partition
Now you are planning to scale the business across continents.
Now let say you started your app in US and your servers and DBs are in Pakistan. Here Requests travelling across continents are having high latency.

What about distributing traffic across data centres? Data centres across continents. Here you will create replicas of your setup accorss the continent which you will called Data centres. Enable cross data centre replication which helps disaster recovery. This always maintain Availability of your system.

Now, Plan for an IPO: Initial Public offering, when a private company sells shares of its stock for the first time to the public and becomes a public company. When a company makes this transition, it is no longer in the hands of the private owners and investors but is now under public ownership.


# CAP Theorem:
CAP stands for consistency, availability and partition tolerance. CAP theorem is one of the most important concept in distributed systems. It states that "In a disributed database system only two of the properties out of CAP can be exist together. It is not possible that a distributed system can have all 3 CAP properties"

**Hypothetical Situation:** There is a situation when all 3 CAP properties can exist together. That situation is when you have a single node (in other words your system is not distributed).

CAP theorem tells if the communication between the nodes get lost then in that case how system will behave? In case of communication loss you have to compromise on one thing our of CAP. which totally depends upon your business requirement.
**CAP Theorem NoSQL Databases:** NoSQL databases are great for distributed networks. They allow for horizontal scaling, and they can quickly scale across multiple nodes. When deciding which NoSQL database to use, it’s important to keep the CAP theorem in mind.

1) **Consistency:** In a consistent system, all nodes see the same data simultaneously. If we perform a read operation on a consistent system, it should return the value of the most recent write operation. The read should cause all nodes to return the same data. All users see the same data at the same time, regardless of the node they connect to. When data is written to a single node, it is then replicated across the other nodes in
the system.

2) **Availability:** When availability is present in a distributed system, it means that the system remains operational all of the time. Every request
will get a response regardless of the individual state of the nodes. This means that the system will operate even if there are multiple nodes
down. Unlike a consistent system, there’s no guarantee that the response will be the most recent write operation.

3) **Partition Tolerance:** When a distributed system encounters a partition, it means that there’s a break in communication between nodes. If a system is partition-tolerant, the system does not fail, regardless of whether messages are dropped or delayed between nodes within the system. To have partition tolerance, the system must replicate records across combinations of nodes and networks.

**We can have three combinations of either two properties:**
## CA Databases:
CA databases enable consistency and availability across all nodes. Unfortunately, CA databases can’t deliver fault tolerance. In
any distributed system, partitions are bound to happen, which means this type of database isn’t a very practical choice. It sounds wierd, that in case of communication loss your data is remain available, this makes sense, but your data will remain consistent too, this do not make sense as when there will be a connection lose between the nodes and system is not shutting down it is accepting request so data can be available but consistency is not possible. So we can say CA is not a practical choice.

## CP Databases:
CP databases enable consistency and partition tolerance, but not availability. When a partition occurs, the system has to turn off inconsistent nodes until the partition can be fixed. MongoDB is an example of a CP database. It’s a NoSQL database management system (DBMS) that uses documents for data storage. It’s considered schema-less, which means that it doesn’t require a defined database schema. It’s commonly used in big data and applications running in different locations. The CP system is structured so that there’s only one primary node that receives all of the write requests in a given replica set. Secondary nodes replicate the data in the primary nodes, so if the primary node fails, a secondary node can stand-in. In banking system Availability is not as important as consistency, so we can opt it (MongoDB). CP database examples are our banks. where consistency is prioriy. We can afford availability but not inconsistency. Therefore, you may have noticed that our fintech apps get down as there is some problem so to maintain consistency of data in distributed systems they shut the connection lose nodes.

## AP Databases: 
AP databases enable availability and partition tolerance, but not consistency. In the event of a partition, all nodes are available, but they’re not all updated. For example, if a user tries to access data from a bad node, they won’t receive the most up-to-date version of the data. When the partition is eventually resolved, most AP databases will sync the nodes to ensure consistency across them. Apache Cassandra is an example of an AP database. It’s a NoSQL database with no primary node, meaning that all of the nodes remain available. Cassandra allows for eventual consistency because users can re-sync their data right after a partition is resolved. For apps like Facebook, we value availability more than consistency, we’d opt for AP Databases like Cassandra or Amazon DynamoDB. But one thing here to not that once the lost connection between the node get resolved the data will be eventually consistent, it will be updated. So we can say AP Databases are eventually consistent. If your business can tolerate eventually consistency then you can go for this type of DB.


# BASE properties
Similar to AP DB there are some properties called BASE properties. These are the principles which are implemented in our social media apps.

1)**Basically Available**
This property refers to the fact that the database system should always be available to respond to user requests, even if it cannot guarantee immediate access to all data. The database may experience brief periods of unavailability, but it should be designed to minimize downtime and provide quick recovery from failures.

2) **Soft State**

This property refers to the fact that the state of the database can change over time, even without any explicit user intervention. This can happen due to the effects of background processes, updates to data, and other factors. The database should be designed to handle this change gracefully, and ensure that it does not lead to data corruption or loss.

2) **Eventual Consistency**

This property refers to the eventual consistency of data in the database, despite changes over time. In other words, the database should eventually converge to a consistent state, even if it takes some time for all updates to propagate and be reflected in the data. This is in contrast to the immediate consistency required by traditional ACID-compliant databases.


**NOTE:** here you have noticed that availability and partitioning tolerance is our main priority. So here in case of any connection loss between the nodes we are compromising on consistency. We are going for eventually consistency principle. Which means that in case of any connection lose we will keep accepting and sending request to our nodes. and once the connection is back establish then consistency will be maintained.

The primary difference between the two is that ACID requires immediate consistency, while BASE only requires eventual consistency. 


# Master-Slave architecture
This architecture is exactly the Pattern 3 which we had studied above in the scalling patterns lectures. The concept is same that we create a replica of the primary DB (Master DB) which deals with the write request and it replica deals with the read request only. In case of primary/master DB failuer. Replica will handle some requests.

There is an interface where requests are comming. These requests pass through the load balancer. The load balancer then pass these requests to the server which is less bussier. And then All these servers are connected with a single DB. If this DB get fails then the whole system will be get crashed. So to prevent and to scale our database we create a replica or master DB and called it as slave.

Here master will look for write requests and slave will look for read requests.

Master-Slave is a general way to optimise IO in a system where number of requests goes way high that a single DB server is not able to handle it efficiently. Its a Pattern 3 in LEC-19 (Database Scaling Pattern). (Command Query Responsibility Segregation). The true or latest data is kept in the Master DB thus write operations are directed there. Reading ops are done only from slaves. This architecture serves the purpose of safeguarding site reliability, availability, reduce latency etc . If a site receives a lot of traffic and the only available database is one master, it will be overloaded with reading and writing requests. Making the entire system slow for everyone on the site. DB replication will take care of distributing data from Master machine to Slaves machines. This can be synchronous or asynchronous depending upon the system’s need.
