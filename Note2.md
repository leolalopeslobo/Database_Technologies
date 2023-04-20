<h1>Normalization</h1>

**RDBMS contains of Table**

Model 1: Stage 1 -> Conceptual:
- Creation of Entity Names
- Creation of Entity Relationships


Logical:
- Primary and Foreign Keys are defined at this stage.


**Physical**:
- When both Conceptual and Logical models are redy, specific system/toll/application is been choosen to built in data
- At this stage we decide which DBMS software application to use
- Specification are drawn for all tables and columns
- **Physical considerations maybe cause the physical data model to be quite different from the logical data model**
- **This model is direct interface to user of Database system**
Here the user interacts using applications, scanners, barcodes that are developed for the purpose
- **Developers** play bigrole in this model
- **Output -> Database Creation in Software**

<h2Noramlization & Forms</h2>
Normalization: This is the process of filtering (filtering is the act of removing something unwanted) in simple words
**It's process with systematic apprach of decomposing tables to eliminate...**
    **- Data Redundancy (Repetition)**
    **- Undesirable characteristics like Insertion, Update and Deletion Anomalies**
    
Data Redundancy: <br>
![image](https://user-images.githubusercontent.com/83197830/233012922-fa83de09-ec10-462f-affe-39a5a2748bdd.png)
In the above table we can see that for all those customer who have purchased mouse product & product price columns are repeated
This is called 'Data Redundancy'

This can lead to **Insertion Anomaly**
Since for every entry we have to maintain that correct order of inserting the correct values and there every chances that by mistake we can make errors since we are dealing with huge amounts of data and only using a single table

This also may lead to **Updation Anomaly**
Since again we need to check that we are updating correcting

There is also **Deletion Anomaly**
Since here again we need to check that each order needs to be deleted according to what has been removed and not other enteries


Inorder to eliminating the above anomalies..
We use perform systematic 'normalization'..
**First Normal Form**
-> For a table to in **First Normal Form....**
  - **Every Cell in that table must contain one and only one value.**
  - A relation is in first normal form if every attribute in that relation is **Singled Valued Attribute**

![image](https://user-images.githubusercontent.com/83197830/233223234-0eea5be2-306a-401b-8a7b-4a545d3d2be7.png)
The above table is not in a first normal form because of the first name and last name are in a single cell, and this is duplicate data since we so many people with the same names, hence we separate them out, which gives us more Accuracy. This makes it easier for us **to perform 'Search operations' based on their first names or last names**

SOLUTION:
Hence this table changes to...
![image](https://user-images.githubusercontent.com/83197830/233223840-e36f0a7a-455b-48c6-a199-32c319b39bf6.png)

Therefore for example, if its
Name -> First Name, Last Name
Address -> HNo, Block No, Street Name, State, Country


**Second Normal Form**
-> For a table to be in **Second Normal Form**
  - Table must be in **First Normal Form**
  - **Every non-prime attribute should be fully functionally dependent on prime key attribute**

![image](https://user-images.githubusercontent.com/83197830/233224232-71b31af5-606f-433a-8b81-716279eda0b3.png)
In the above image
Entity: Customer
Attribute (primary key): Customer ID
Whatever is the primary key is the prime key attribute


From the above picture,
if we know the CustomerID (which is the primary key) can I get to know the,
  - First Name (YES)
  - Last Name (YES)
  - Age (YES)
  - Location (YES)
  - Zip (YES)
  - **Product (NO) -  since the Customer can purchase any product and is not restricted to a particular one**
  - **Cost (NO) - since this depends on the product purchased**

SOLUTION:
Here we divide this one table into multiple tables and make it 'Second Normal Form
![image](https://user-images.githubusercontent.com/83197830/233225163-8e160bea-7088-4876-a939-ec16a0e214ed.png)

The Customer is not directly linked to the Product, but gets connnected once the Order is made
Here we are 'Storing the data at one place', so only one change is made and accordingly everything is updated

**Rememeber: In a single table there can never be 2 primary keys, they are 2 attributes that help or when combined make up a Primary Key, that's called Composite Primary Key**

By Separating we are not having having Inserting, Deletion or Updation Anomalies


**Third Normal Form**
-> For a relation to be in the Third Normal Form,
  - It must be in Second Normal Form and the following must satisfy......
  - **No Non-Prime attribute is _transitively_ dependent on Primary Key attribute**

![image](https://user-images.githubusercontent.com/83197830/233226276-b6b1eb55-6f94-4c14-8105-b92f6ce13375.png)
In the above picture,
Location is not fully given and is not dependent on CustomerID but in the Zipcode

SOLUTION:
![image](https://user-images.githubusercontent.com/83197830/233226425-386f324e-ebd8-4b44-90f4-8de0f87c6db1.png)

In every situation we don't have to go to the Third Normal Form, but in all cases that depend on the Address, like Swiggy, E-Commerce, etc.



**Boyce Code Normal Form**
Used only for special purposes
Its stricter than the Third Normal Form
When a realtion has more than one candidate key, anomalies may result even though the relations is in 3NF
3NF does not deal satisfactorily with the case of a relation with overlapping candidate keys

![image](https://user-images.githubusercontent.com/83197830/233227016-9932de51-e3de-4a5d-be62-fb1655039e9a.png)

Then it becomes
![image](https://user-images.githubusercontent.com/83197830/233227128-76f6a5d0-0c28-41e8-a8b5-bddb514ca6e8.png)


Usually we mandatorily require 2 Normal Forms, the Third Normal Form is not really required but incase its not required
and Boyce Codd Normal Form is for specific purposes

<h3>Codd's 12 Rules for a Relational Database</h3>
There is a 12 Test for a Software Applications must pass these rules to become a RDBMS

First Rule 1:
The information rule
  All Data must be stored in the form of **Table** Cell
  
Second Rule 2:
The guaranteed access key
  Each unique piece of data(atomic value) should be accessible ONLY by : Table Name + Primary Key(Row) + Attribute(Column)
  (In short there must be only one primary key or a facility to create a primary key)
  Primary Key should be unique and also continue to be unique
  
  
Third Rule 3:
Systematic treatment of null values
Null is something that we can't determine
  It should be handled consistently
  It should have only one of the following three meanings -> **missing data, not applicable or no value**
  **PRIMARY KEY MUST NOT BE NULL, EVER!**
  
 
Fourth Rule 4:
Active Online **Catalog**
(Online means at the same place when you are storing the database)
It gives us an outline/summary
**And this data is data about the data called Meta Data**
  Database dictionary (catalog) is the structure description of the complete Database and it must be stored online
  In MySQL is called as 'Information_Schema' - Catalog
  The Catalog must be givered by same rules as rest of the database
  
  


Fifth Rule 5:
The comprehensive data sublanguage rule
  A database can only be accessed using a language having linear syntax (linear syntax means english language) that supports data definition, data manipulation, and transaction managaement operation (this also made it popular since the language was simple and plain). Eg: SQL
  If the database allows access to the language without the use of this language, then that is a validation
  
  
  
  
Sixth Rule 6:
View Updation Rule
  All the view that are theoretically updatable should be updated by the system as well
  This is **consistency**, it reflects the change on all the places
  
  
  
Seventh Rule 7:
Relational Level Operation
  There must be Insert, Delete, Update operations at each level of relations (mandatory)
  Set operation like Union, Intersection and Minus should also be supported
  In MySQL has Union
  


Eigthth Rule 8:
Physical Data Independence
  The physical storage of data should not matter to the system
  (This means that wherever you store the data, maybe on the Mumbai Server or on the Hydrabad Server, and if data files are moved, it should not matter)
  If say, some files supporting table is renamed or moved from one disk to another, it should not affect the application
  **Specially this is done so that when there a load on one server you can move the files without the application getting disturbed, all you need to do is configure the IP address of that server**
  
  
  
Ninth Rule 9:
Logical Data Independence
  If there is change in the logical structure (table structures) of the databases the user view of data should not change
  If the table is split into two tables, a new view should give result as the join of the two tables (why? would you do this? -> This is done because as the data size grows larger we need to increase the search efficiency). When they still join back they result in the single table output and this can be done using the concept of **View**
  
  
  
Tenth Rule 10:
Integrity Independence
   Why do we defined Primary Key?
   By doing this maintain **Data Integrity/Data Validation**. We make sure that there are no garbage (repeated, null) values
   The database should be able to enforce its own integriyrather than using other programs
   **Key and Check constraints, triggers etc, should be stored in Data Dictionary. This also makes RDBMS independent of front-end
   
   
   
What are all these contraints?
**Constraints are used for Data Validation**. Protecting data from garbage data.
**Constraints are: PRIMARY KEY, FOREIGN KEY, CHECK (MySQL find out how it works), UNIQUE, NOT NULL, ENUM**

Difference between Database and Data Warehousing?
Database: Here we want only 'Structured' data, Validation is important
DataWarehousing: Here 'unstructured' data is stored, No Validation or Self-Validation is done
  


Eleventh Rule 11:
Distribution Independence
   This helps achieve **Data Security**
   A database should work properly regardless of its distribution across a network
   Even if a database is geographically distributed, with data stored in pieces, the end user should get an impression that is stored at the same place
   (This means that the same server is logically distributed into multiple servers)
   Why is it necessary?
   This helps incase one of the server crashes the others are there to provide and continue with the work
   This lays the foundation of distributed database (like cloud)
   
   
   
   
Twelveth Rule 12:
Non Subversion Rule
   If low access is allowed to a system it should not be able to subvert or bypass integrity rules to change the data
   (This means no matter how ever you are importing or exporting you can bypass the integrity rules)
   This can be achieved by some sort of locking or encryprion
