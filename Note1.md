<h1>Introduction to DBMS</h1>

What is Data? <br>
- **Facts** in the form of **numbers** or reports
- Values of **qualitative** or **quantitative** variable
- Often collected for references or analysis. It's collected for a **purpose** or **task** Eg.: Temperature of city collected over the years.
- Used as a basis for discussion, reasoning or calculation
- In computing world, it's a information processed or stored by a computer
- This information may be in the form of text documents, images, audio clips, software programs, or other types of data

Fact: Can be text or verbal data
Numeric: This is data in the form of numbers

Qualitative: These data are mostly described using **adjectives**. Eg: Summmers in India are **very** high. <br>
high, low, extremely, very <br>
Quantitative: Any data that involves numbers. Eg: The temperature in India is **40 degree** celcius. <br>

Companies usually analysis are done when they want to enter the market. Bussiness decisions are never random decisions.

Earlier, data was in the text form (everything handwriting, photocopies, everything was in the physical form). Now everything everything is in the digital form.

What is Database? <br>
Collection of data, when data is dumped together it becomes a database. <br>
All databases are not relevent. <br>

HEAP: If data is unorganised then it not a database, but instead called **heap**
In real world we face a lot of challenge to work with these kinds of data

- Collection & Storage of Data
- Collection of facts and figures
- Maybe related or unrelated directly <br>
Intially all the data is not relation, until you have a purpose you can't relate the data. Once you get the purpose you which to study that data and create **relations**


DBMS (Database Management System)
You have a database now you require a system to manage it, and this system is called **Database Management System (DBMS)**
DBMS are **software applications**

DBMS software applications:
PART1:
dBase (1978)
Clipper (1985)
FileMaker (1985)
FoxPro (1994)
**Oracle (1979)** - revolutionary of DBMS
**Microsift SQLServer**
**MySQL (1995)**
**PostgreSQL (1986)**

PART2:
**MongoDB (2007)**
**Cassandra (2008)**


**The major difference between PART1 databases and PART2 databases are that PART1 was in the range of SQLs wheres the PART2 was in the range of NoSQLs.** Hence PART2 was doing everything opposite to that of PART1.
Like its organizations and how they we accessed


Areas of Utilization of DBMS
It is used almost **everywhere**, to name a few Banking, Manufacturing, Governments, Medical, Managaement, etc...



Types of DBMS:
Structually there are three types of DBMS
1. **Relational Databases**
These contain **tables**. Here there exists **relations/relationships (they are interconnceted)** between the tables
Eg: Oracle, MSAccess, MySQL, PostgreSQL, Sybase, DB2, Informics, etc..
2. **Object Relational Databases**
3. **NoSQL**
MongoDB, Cassandra, HBase, NeoForte, CouchDB, etc..


**Relational Databases**
- Most widely and commonly used model of database, since it's there from the very beginning
- Data is stored in the form of **TABLES** also known as relations
- Each  table consists of rows & columns
- Each row is a record also known as tuple
- Introduced by **E.F. Codd** in **1970**

**It became popular, becaused it used the concepts of tables and that everything from young age is in the form of tables, and this was very easy to understand.**
In NoSQL, there are **no tables**


**Object Relational Database**
- Similar to RDBMS
- It incorporates tables, but isn't limited to tables, hence can also be known as Hybrid Database Models
- It has Object-Oriented database model such as Objects, Classes and Inheritance directly supported by in database schema and in query language
- Best known as Post-Relational Database Model
- Multimedia database incorporates media, such as images


**NoSQL**
- No SQL or Not Only SQL
- Highly useful for **unstructured** data specially data type of incoming data can not be defined before hand.
- Generic data model (sets, maps & arrays) - **sometimes defining explicit data type not necessary**
- Dynamic type discovery and conversion
- Usually non related and de normalized data (row format data) (since these are usually need based relations)
- Highly distributable
- Commodity hardware - Adding more economical hardware at later stages is possible


What is **Structured Data**?
The **type of this data is known**

What is Unstructured Data?
The **type of data is not known**



Data Modeling
This means how the database is built
3 parts/stages/models:
1. Conceptual
2. Logical
3. Physical


**Conceptual**:
- High-level description of a business's information (understanding the business working, its needs, etc.)
- A first-cut model, with insufficient details to build an actaul database (like a rough map, flowchart, etc..)
- Business Analyst play import role at this stage
- **Output -> Entity Relationship(ER) Diagram**

ER Diagram: <br>
![image](https://user-images.githubusercontent.com/83197830/232982700-2988ab4b-727b-471c-8999-7effef9da5cf.png)


Eg: School Management System
Student
    - studentid(rollno)
    - name
    - gender
Teacher
Classroom
Course
    - CourseId
    - Fees
    - Duration
    - name
    - seats
    
Relationships
Student ---- Course
Student ---- Teacher


**Logical**:
- Describes the data in as much as details as possible
- Includes all entities and relationships among them
- All attributes for each entity are specified
- The **primary key** for each entity is specified. **The primary key is an attribute for an entity that can't be and wont be duplicated like a 'unique value'**
- **Foreign key** (keys identifying the relationship between different entities) are specified.
- **Normalization** occurs at this level
- Specific RDBMS chosen later stage will not have any impact on this model
- Data Architect will play major role at this stage
- **Output -> Database Schema**
Scheme means organizing and dividing into tables

**Note: For RDBMS, if we learnt one, we learnt all. They use the same principles.**

Note: A table can only have one primary key
