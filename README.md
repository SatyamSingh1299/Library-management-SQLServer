# Files
This repository contains several files that are integral to the setup and execution of a database management system for a library. 
Here's a brief overview of each file:

**SatyamSingh_Report_CS504_002.pdf**: A comprehensive report detailing the project work.  
**LibraryScript.sql**: This SQL file is used to create the database, tables, and schemas, and then populate the tables with data.  
**README.txt**: This text file contains details of the files and instructions for running the code.


# Instructions to Execute
**Setting up the Database**: Open the database LibraryScript.sql file in any SQL editor.  
**Executing the Queries**: Select all contents and run it to create the database, tables, schemas, and insert the data into the tables.  

# Library-management-SQLServer
This project aims to develop a library management system for a public library which can help in 
tracking of the library resources. As a library consists of different types of materials, managing 
everything via traditional methods would be lengthy and can be faulty as well. Using a Relational 
database at this scenario is the perfect fit as it can add many other facilities. For this database system 
to be in a proper form so that data integrity is maintained we must go according to the guidelines.

In this Library Database we have 7 entities and many attributes within,

1. Material
2. Borrow
3. Author
4. Catalog
5. Genre
6. Member
7. Staff

# Details
Designed and implemented a full data management system on SQL Server.  
The project utilized databases, schemas, sequences, and views to organize data, and incorporate Tasks for workflow automation and data validation.  

Created dedicated databases, schemas, and tables using SQL Server DDL statements.  
Used SQL Server’s CREATE TABLE and CREATE SCHEMA commands to design normalized data structures.  
Designed up to the Third Normal Form (3NF). Each entity such as Material, Genre, Catalog, Author, Member, Staff, and Borrow has its own table, eliminating redundancy.  
References between tables are handled via foreign keys (e.g., Material to Genre, Borrow to Member), ensuring each attribute is atomic and dependent only on its table’s primary key.

**Views for Reusable Analytics and Reporting**  
Created multiple views to support repeated analytical queries such as monitoring overdue materials, counting borrows by member, or referencing top borrowed books.

CREATE OR REPLACE VIEW Borrow_Summary AS  
SELECT MemberID, COUNT(BorrowID) AS TotalBorrows, SUM(DATEDIFF('day', BorrowDate, DueDate)) AS BorrowDays  
FROM Borrow
GROUP BY MemberID;
