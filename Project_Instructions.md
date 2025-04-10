# Project Instructions

## Overview
Bits & Books needs a simple information management system and database to support their inventory and sales operations.  

You and your teammates will work on this project independently throughout the semester. You will receive feedback (but no points) for submitting four checkpoint documents. 
 
The project overview document, worksheets, and sample data will help you with many of the user requirements. In addition, to receive full credit for your project, you will be required to come up with extensions that expand on the requirements here and provide new functionality beyond the scope of the basic requirements. 

---

## Final Project Document
The final report must be:
- Professionally presented
- Well-organized
- Typed

It must be submitted electronically to the Carmen Dropbox in a single ZIP file. This ZIP file needs to be:
- Neatly and professionally organized
- Contain appropriately chosen filenames
- Include all files suitably organized into subdirectories

### Table of Contents
Include a `README.txt` file that explains the layout of your files, including where to find each of the following:

---

### Part I – The Final Report
Your final document will include:
- A relational database schema
- An entity-relationship diagram
- SQL queries
- Reports

#### Section 1 - Database Description
A database description document that contains the following:
1. **ER-Model**  
   - A professionally presented, well-formatted ER-model reflecting updates made during the semester.  
   - Do not submit a hand-drawn diagram.

2. **Relational Schema**  
   - A professionally presented, well-formatted relational schema for the database.  
   - Annotate the schema with:
     - Primary keys for each table
     - All foreign keys on all tables
     - All functional dependencies on all tables  
   - Ensure connections between FKs and PKs are clear.

3. **Normalization**  
   - For each table, provide:
     - A brief description of the level of normalization achieved.
     - If the table is not in BCNF, explain why.

4. **Indexes**  
   - Describe each index implemented on your database.
   - Provide a rationale for each index.

5. **Views**  
   - For each view implemented, provide:
     - A brief description in English of what the view produces and why it is useful.
     - Relational algebra expression to produce the view.
     - SQL statements to produce the view.
     - Sample output from the view (5-10 lines of data records).

6. **Sample Transactions**  
   - Provide three sample transactions useful for your database.  
   - Include:
     - Sample SQL code for each transaction.
     - An English description of the "unit of work" the transaction represents.  
   - Example: A user making changes to an order.

---

#### Section 2 - User Manual
A user manual describing the usage of your database for developers writing code to use it. Include:

1. **Table Descriptions**  
   - For each table, explain:
     - The real-world entity it represents.
     - A description of each attribute, including its data type and constraints.

2. **Sample SQL Queries**  
   - Include the queries provided in Checkpoints 02 and 03.  
   - For each query, provide:
     - An English description of what the query returns.
     - The correct relational algebra syntax.
     - The equivalent SQL query.

3. **INSERT Syntax**  
   - Provide syntax for adding new books, publishers, authors, and customers.  
   - Indicate any dependencies requiring specific order of record additions.

4. **DELETE Syntax**  
   - Provide syntax for removing books, publishers, authors, and customers.  
   - Indicate any dependencies requiring specific order of record deletions.  
   - Include example DELETE statements for each entity.

---

#### Section 3 - Graded Checkpoint Documents
An appendix containing all original, graded checkpoint documents.  
- Organize them neatly and professionally.  
- For revised checkpoints, include a pointer to the updated version in the final report (e.g., "See Section X Page Y for the new relational model diagram").

---

### Part II – The SQL Database
Your submission must include:

1. **Binary Database**  
   - A binary version of your database, suitable for opening using either the `sqlite3` command-line tool or the Firefox SQLite Admin tool.

2. **SQL CREATE**  
   - A text file containing all scripts needed to create your database schema on an empty database.  
   - Ensure the file:
     - Is properly commented.
     - Executes properly when pasted into an SQLite command prompt or loaded from the command-line tool.  
   - Include all indexes and views.

3. **Data Files**  
   - Provide text files containing the data to be loaded into your database.  
   - Include instructions on how to use these scripts and files in a separate text file.

4. **SQL Queries**  
   - A text file containing all SQL queries used in your final report.  
   - Ensure the queries:
     - Can be run over your database through simple cut-and-paste.
     - Are fully commented to indicate their origin in the final report.

5. **SQL INSERT/DELETE**  
   - A text file containing all sample INSERT and DELETE statements from your user manual.  
   - Ensure they are suitable for pasting into a command prompt and testing.

---

## Worksheets and Checkpoints
You will work on the project incrementally throughout the semester.  
- Submit four checkpoint (draft) documents for feedback.  
- Use the worksheets and sample data as guides for developing project ideas.