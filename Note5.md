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
  
