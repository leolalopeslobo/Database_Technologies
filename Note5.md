<h1>Learning More Queries</h1>

---------------
**distinct** - this give us the distinct/uniques values of an attribute
<h3>select distinct(designation) from employee;</h3>
---------------

----------------
**GROUP BY** - this lets us get a count of the number of times a particular entity has repeated
<h3>select designation, COUNT(designation) from employee GROUP BY designation;</h3>
Remember: GROUP BY clause should always be at the last in a query


So when you need to specify a condition then that needs to come at the end and GROUP BY doesn't allow this since it needs to be declared at the end, hence instead of WHERE for a condition use **HAVING**

--------------------


---------------------
<h3><> or != (Not EQUAL)</h3>
------------------------------
  
  
-------------------
**Query Within a Query** or **Sub-Query**
<h3>select efname, salary from employee where salary = (select max(salary) from employee);</h3>
-----------------------
  
  

-----------------------
<h2>EXISTS and NOT EXISTS</h2>
This is good when we need the outer query to execute when at least on of the inner query is true.
------------------------


-----------------------
<h2>UNION</h2>
<h3>select * from member1 UNION select * from member2;</h3>

<h2>UNION ALL</h2>
<h3>select * from member1 UNION ALL select * from member2;</h3>
----------------------


-------------------------
<h1>INTERECTION</h2>
It is used to get/obtain only the common elements
Acc' to Codd's Rule, Intersection is not directly supported by MySQL
Hence we use a WHERE clause with IN and a SUB QUERY to get the INTERSECTION
--------------------------


-----------------
<h2>MINUS</h2>
MINUS is also not supported hence it can be achieved using WHERE clause with NOT IN with SubQuery
-----------------


Remember: **after** is present for but **before** is not avaliable


--------------------
ucase - Upper Case
lcase - Lower Case
left - used for trimming strings from left side
right - used for trimming strings from right side
-------------------

------------------------
<h2>AUTO INCREMENT</h2>
What is Auto_Increment?
Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table. Often this is the primary key field that we would like to be created automatically every time a new record is inserted.
-------------------------



-----------------------
<h2>CREATING NEW USERS</h2>
<h3>create user abc@localhost IDENTIFIED BY 'mm';</h3>
we need to mention that localhost since we are creating on the same host
mm - here is the password

Here we created the user from 'root'


<h2>DISPLAYING THE USERS</h2>
<h3>select User from mysql.user;</h3>


<h2>GRANTING PRIVILAGES</h2>
<h3>grant select ON cdac_db.* TO abc@localhost;</h3>


<h2>TAKING BACK PRIVILAGES FROM CREATED USER</h2>
<h3>REVOKE select ON cdac_db.* FROM abc@localhost;</h3>
