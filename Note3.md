<h1>Creating Tables</h1>


To eliminate Data Redundancy, we should have separate tables for different entities.

Third Normal Form is only done when you require more detailing, usually it's not done

First Normal, Second Normal is done after the Data Schema


<h2>How To Write Queries using SQL to MySQL</h2>
SQL is not Case-Sensitive
Open **Command Prompt**
<h3>mysql -u root -p</h3> - to connect to MySQL from CMD
Enter Password
<h3>show databases;</h3> (like catalog for databases)
<h3>drop database _database_name_;</h3>
<h3>CREATE DATABASE _database_name_;</h3>
<h3>use _database_name_</h3>
<h3>show tables</h3> (like catalog)

Difference between **char** and **varchar** datatypes
**Char hold a fixed length string**
**Varchar holds a variable length string. Here even if we initially fixd the size as 10, and gave input of size 2, automatically the varchar adjusts itself and allocates a size of 2**


**Enum: This lets you choose only from the give options**
**; - means that the you have finished typing the query, called as a 'terminator'**


**QUERY OPTIMIZSER: This is an engine that will execute the queries**


create table book
(
	bookid varchar(10) PRIMARY KEY,
	bookname varchar(20),
	authorid varchar(20),
	category varchar(20),
	cost int(20),
	noofpages int(10),
	rackid varchar(10),
	**bookstatus enum('A', 'NA', 'O'),**
	pushisherid varchar(10),
	booklastissueddate date,
	booklastissuedtime time,
	foreign key(authorid) REFERENCES author(authorid)
);


create table author
(
	authorid varchar(10),
	authorname varchar(30),
	nationality varchar(20),
	gender enum('M','F')
);


<h3>alter table _table_name_ add primary key(_attribute_name/column_name_);</h3> - the ALTER keyword here is used to change the **structure** of the table (like change -> add/remove/modify columns, declare constraints)
**Alter is not for the values it is for the structure**
This above command is to add a constraint like declared the primary key



<h3>desc _table_name_</h3> - this provides us details about the table


Constraints -> Used for **'Data Validation'**
- Foreign Key
- Primary Key
- Unique
- Not Null
- Default
- Check (doesnt work in MySQL, though it won't be an error)
- Enum

- Trigger

<h2>Adding Values into the Table</h2>
<h3>INSERT INTO _table_name_ VALUES (_supply_data_);
  
**Remember always enter the values in the master table, and then in the other tables that depend on it**
  
  
<h2>How to see the values/data that is entered into the table</h2>
<h3>select * from _table_name_</h3> - * means all
  
<h3>Insert into _table_name_ values ('B001', 'One Night at Call Centre', 'A003', 'Fiction', 300,240,'R001','A','P001',**'2020/05/22'**,**'14:00'**);</h3> - taking in **date** and **time**
  
  
<h2>Altering Table through Modifying the column varchar size</h2>
<h3> alter table _table_name_ modify column _column_name_ varchar(60);</h3>
  
  -----------------
  UNIQUE CONSTRAINT
  -----------------  
  <h2>Understanding how **Unique** works</h2>
  Unique can take null
  No duplicates allowed
  
  
  <h2>How can you delete all the data from the table at once</h2>
  <h3></h3>
  
  <h2>How can you delete certain desired data entries from the table</h2>
  <h3>DELETE FROM _table_name_ WHERE _column_name_ is _value_</h3>
  
  ------------------
  NOT NULL CONSTRAINT
  ------------------  
  <h2>How to make an attribute **not null**</h2>
  <h3>ALTER TABLE _table_name_ MODIFY COLUMN _column_name_ _datatype_ NOT NULL;</h3>
  
  
  ------------------
  DEFAULT CONSTRAINT
  ------------------
   <h2>How to make an attribute **default**</h2>
  <h3>ALTER TABLE _table_name_ MODIFY COLUMN _column_name_ _datatype_ DEFAULT _default_value_;</h3>
  **alter table author modify column gender enum('M','F') DEFAULT 'M';**
  
  This allows us to enter only the values that are not metioned as default
  
  
  ----------------
  CHECK CONSTRAINT
  ----------------
   <h2>How to make an attribute as **CHECK**</h2>
  <h3>ALTER TABLE _table_name_ MODIFY COLUMN _column_name_ _datatype_ CHECK (_column_name_= value or _column_name_= value);</h3>
  **aalter table author modify column nationality varchar(20) CHECK(nationality='India' or nationality='Singapore');**
  
  
  
  --------------
  ANOTHER WAY TO LEARN ABOUT THE TABLE BESIDES USING 'DESC'
  --------------
  <h3>show create table _table_name_;</h3>
  
  
  -----------
  TRUNCATE
  ----------
  This is one go eliminates all the data, removes/deletes all the data of the in the table at once
  <h3>truncate table _table_name_;</h3>
  
  
  ---------
  RENAME A TABLE
  -----------
  <h3>alter table _oldTableName_ rename _newTableName_;</h3>
  
  
  
  ---------------
  How to Remove Constraints
  ---------------
  ????
  
  
  ---------
  UPDATE
  ---------
  <h3>update newauthors set authorname = 'Devika Rai';</h3>
  <h3>update newauthors set authorname = 'Chetan Bhagat' **where** authorid = 'A001';</h3>
  
  
  
  Remember **delete query without where will function like truncate only and delete all the records from the table**
  Remember anything without the where condition affects the entire table records
  
  
  
  
  
  
  
  
  
  










