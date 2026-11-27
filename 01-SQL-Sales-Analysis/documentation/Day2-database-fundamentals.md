\# Day 02: Database Fundamentals



\## 1. What is a Database?

\## 2. What is a DBMS?

\## 3. What is a Table?

\## 4. Rows and Columns

\## 5. Primary Key 

\## 6. Foreign Key

\## 7. How SQL Works





Lesson 1 — What is a Database?



ধরো, একটি Supermarket আছে। প্রতিদিন সেখানে অনেক customer পণ্য কিনছে।



দোকানটির কাছে বিভিন্ন তথ্য জমা হচ্ছে:

\- Customer information

\- Product information

\- Order information

\- Sales information

\- Payment information

এত তথ্য যদি আলাদা আলাদা কাগজে বা Excel ফাইলে রাখা হয়, তাহলে সবকিছু manage করা কঠিন হবে।



তাই দোকানটি একটি Database ব্যবহার করে।



Definition (English):



A database is an organized collection of data that can be easily stored, accessed, managed, and updated.



বাংলায়: Database হলো এমন একটি সংগঠিত জায়গা যেখানে অনেক তথ্য সুন্দরভাবে সংরক্ষণ করা হয়, প্রয়োজন অনুযায়ী খুঁজে বের করা যায় এবং পরিবর্তন করা যায়।



Real-life examples:

Organization	Database information

Bank	Customer accounts and transactions

Hospital	Patient and medical records

University	Student and course records

Supermarket	Products and sales

E-commerce	Orders and customer details



Remember: Database শুধু তথ্য জমা রাখার জায়গা নয়। তথ্যকে organized রাখাও এর গুরুত্বপূর্ণ কাজ।









Lesson 2 — What is a DBMS?



এবার প্রশ্ন হলো, Database তৈরি ও পরিচালনা করবে কে?

এখানে আসে DBMS.

DBMS = Database Management System



Definition:



A DBMS is software that allows users to create, store, manage, retrieve, and manipulate data in a database.



বাংলায়, DBMS হলো এমন একটি software যার সাহায্যে আমরা Database তৈরি, পরিচালনা এবং সেখান থেকে তথ্য বের করতে পারি।



কিছু জনপ্রিয় DBMS:

\- Microsoft SQL Server

\- MySQL

\- PostgreSQL

\- Oracle Database

\- SQLite

আমরা কোনটি ব্যবহার করছি?



আমরা ব্যবহার করছি Microsoft SQL Server 2025.



এটি আমাদের Database Management System.



আর SSMS (SQL Server Management Studio) হলো সেই graphical application, যার মাধ্যমে আমরা SQL Server-এর সঙ্গে কাজ করি।



একটি পার্থক্য মনে রাখবে:

Software	কাজ

SQL Server	Database পরিচালনা করে

SSMS	        Database-এর সঙ্গে কাজ করার interface

SQL	        Database-এর সঙ্গে কথা বলার language











Lesson 3 — What is a Table?



Database-এর ভেতরে সাধারণত একাধিক Table থাকে।



Table হলো এমন একটি structure যেখানে information Rows এবং Columns আকারে সাজানো থাকে।



ধরো, আমাদের Superstore-এর Customer Information সংরক্ষণ করতে হবে।



তাহলে আমরা একটি Customers Table তৈরি করতে পারি।



একটি উদাহরণ দেখি:

CustomerID	CustomerName	City

101	        Rahim	        Dhaka

102	        Karim	        Chittagong

103	        Hasan	        Sylhet

104	        Tanvir	        Dhaka



এখানে:

\- Table Name = Customers

\- CustomerID = একটি Column

\- CustomerName = একটি Column

\- City = একটি Column



অর্থাৎ, Table-এর মধ্যে বিভিন্ন ধরনের তথ্য আলাদা আলাদা Column-এ রাখা হয়।









Lesson 4 — What are Rows and Columns?



এটি খুবই গুরুত্বপূর্ণ। SQL শেখার সময় বারবার এই দুটি শব্দ ব্যবহার হবে।

Column = Field / Attribute



Column হলো একটি নির্দিষ্ট ধরনের information.



যেমন: CustomerID, CustomerName, City.



Row = Record



Row হলো একজন Customer বা একটি নির্দিষ্ট record-এর সম্পূর্ণ তথ্য।



যেমন: 101 | Rahim | Dhaka



চলো আবার আমাদের Customer Table দেখি।

CustomerID	CustomerName	City

101	           Rahim	Dhaka

102	           Karim	Chittagong

103	           Hasan	Sylhet



এখানে প্রথম Row-তে Rahim-এর সম্পূর্ণ information আছে।



আর CustomerID হলো একটি Column.



সহজভাবে মনে রাখবে:

\- Row = একটি সম্পূর্ণ record (horizontal).

\- Column = একটি নির্দিষ্ট field (vertical).











Lesson 5 — Primary Key and Foreign Key



A. Primary Key (PK)

ধরো, আমাদের Customer Table-এ দুইজন মানুষের নাম Rahim হতে পারে।



তাহলে শুধু CustomerName দিয়ে আমরা একজন নির্দিষ্ট Customer-কে আলাদা করতে পারব না।



এজন্য আমরা CustomerID ব্যবহার করি।



Definition:



A Primary Key is a column (or combination of columns) that uniquely identifies each record in a table.



বাংলায়: Primary Key হলো এমন একটি Column যার প্রতিটি value আলাদা হয় এবং যা দিয়ে একটি নির্দিষ্ট Row বা Record শনাক্ত করা যায়।



উদাহরণ:

CustomerID(PK)	CustomerName

101	          Rahim

102	          Karim

103	          Rahim



দেখো, দুইজন Rahim আছে। কিন্তু তাদের CustomerID আলাদা।



Primary Key-এর দুটি গুরুত্বপূর্ণ নিয়ম:

1\. Duplicate value থাকতে পারবে না।

2\. NULL value থাকতে পারবে না।

Remember

&#x20;Primary Key uniquely identifies each record.

B. Foreign Key (FK)

এবার একটু অন্যভাবে চিন্তা করো।



আমাদের দুটি Table আছে:



Customers Table

CustomerID (PK)	CustomerName

101	Rahim

102	Karim

103	Hasan



Orders Table

OrderID(PK)	CustomerID (FK)	Amount

5001	             101	1500

5002	      	     102	2500

5003	             101	3000





Customers Table-এ CustomerID হলো Primary Key.



কিন্তু Orders Table-এ CustomerID হলো Foreign Key.



Definition:



A Foreign Key is a column that references a Primary Key in another table to establish a relationship between tables.



বাংলায়: Foreign Key একটি Table-কে অন্য একটি Table-এর সঙ্গে সম্পর্কিত করে।



উদাহরণস্বরূপ, Order 5001 কে Rahim-এর সঙ্গে connect করা যাচ্ছে, কারণ দুই Table-এই CustomerID 101 আছে।





\-Primary Key vs Foreign Key



Primary Key	           		Foreign Key

Uniquely identifies records	Connects related tables

Cannot contain NULL		Can contain NULL in some designs

Unique values			Duplicate values allowed

Identifies a record		References another table



\*\*\* একটি Customer-এর একাধিক Order থাকতে পারে। এটাকে বলে One-to-Many Relationship.













Lesson 6 — How SQL Works

SQL-এর পূর্ণরূপ: Structured Query Language



SQL হলো এমন একটি language যার মাধ্যমে আমরা Database-এর সঙ্গে communicate করি।



যেমন, আমরা Database-কে বলতে পারি:

\- Show me all customers.

\- Find products with sales above 1,000.

\- Calculate total sales.

\- Find the most profitable product.

এই কাজগুলো SQL Query দিয়ে করা হয়।



একটি ছোট উদাহরণ:

SELECT \*

FROM Customers;





এর অর্থ:

\- SELECT = কোন তথ্য দেখতে চাই।

\- \* = সব Column দেখতে চাই।

\- FROM = কোন Table থেকে তথ্য নিতে চাই।

\- Customers = আমাদের Table-এর নাম।

অর্থাৎ, এই Query Database-কে বলছে:



"Customers Table-এর সব তথ্য আমাকে দেখাও।"



SQL-এর কিছু গুরুত্বপূর্ণ command:

Command	কাজ

SELECT	Data দেখা

INSERT	নতুন Data যোগ করা

UPDATE	Data পরিবর্তন করা

DELETE	Data মুছে ফেলা

CREATE	Database/Table তৈরি করা

ALTER	Table structure পরিবর্তন করা

DROP	Database/Table মুছে ফেলা

