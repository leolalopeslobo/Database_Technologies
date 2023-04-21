<h1>Learning about DDL, DML, and DCL Commands</h1>

------------
ROLLBACK
------------
This is used to undo the previous query and works in DML commands only when they are in manual commit mode i.e. autocommit = 0.
Rollbacks undos all the DML commands and only the immediate previous one


----------
SAVEPOINT
----------
Let's you rollback back step by step. It let's you add bookmarks to the desired query you want to rollback to


How to find the list of savepoints?


----------------------------------------------
<h1>Data Retival Commands</h1>
---------------------------------------------
* - means all rows, all columns
select BookId, BookName, Category, Cost from book; - display on desired columns/attributes


Changing the column names temporarily - 'Column Alias'

Use of 'Where' command
WHERE - its allows you to work with selected rows/entries/records (rows based on condition)


---------------
Adding after another specific column
---------------
**alter table table_name add column column_that_needs_to_be_added datatype AFTER column_name_after_which _you_want_to_add;**



----------------------------------------------
<h1>Approximation</h1>
---------------------------------------------


------------------------------------
<h1>Joining Tables</h1>
--------------------------------------
Joining Tables
<h3>Here the _**'Foreign Key'**_ helps in achieveing this</h3>


1. Most basic join
![image](https://user-images.githubusercontent.com/83197830/233573504-c8251f09-2635-4a97-96de-9759cc20eaca.png)

2. Using **JOIN** and **ON**
![image](https://user-images.githubusercontent.com/83197830/233573807-3086c477-9255-4fb2-ba59-3993558b6959.png)

3. JOIN, LEFT JOIN and RIGHT JOIN
![image](https://user-images.githubusercontent.com/83197830/233576745-d0e5dd52-34fe-4d7b-9e98-dc576024ee0c.png)

There are 4 Types of JOINS
1. SIMPLE JOIN, EQUIJOIN, PERFECT JOIN
2. LEFT JOIN
3. RIGHT JOIN
4. SELF JOIN



