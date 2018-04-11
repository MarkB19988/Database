# Database

### Relational Database System Design

#### Tools and Techniques Used

#### Techniques
I created a Entity Relationship Diagram to show how the tables in my database system are related to eachother.

I also created a Data Dictionary to show what information will be stored in each table.

#### Tools
To create my Entity Relationship Diagram I used an online tool called 'draw.io' that cna be used to create a wide variety of table and charts.

To create my Data Dictionary I used Microsoft Excel, a tool used to create tables and graphs and can be used to store values in a spreadsheet

![ERD](https://i.imgur.com/S1zF9uD.jpg)
###### My Entity Relationship Diagram

![DataDictionary](https://i.imgur.com/qYy0eRL.png)
###### My Data Dictionary

#### User Stories

###### As a user I would like to be able to look up my heroes level

###### As a user I would like to be able to look up my enemies level

###### As a user I would like to be able to look up my heroes current health

###### As a user I would like to be able to look up my enemies current health

###### As a user I would like to see how much damage my spells do

###### As a user I would like to see the range of my different spells

###### As a user I would like to see how much damage the enemy does

###### As a user I would like to see the name of my enemies

###### As a user I would like to add new enemies using a form

###### As a user I would like to delete data entries using a form

###### As a user I would like to add new heroes using a form

###### As a user I would like to create a report

###### As a user I would like to use SQL code to add new tables to the database

### Forms, Data Validations and Reports

Below are screenshots of my Forms that have data validation built in and the Report that is generated.

![Imgur](https://i.imgur.com/KMPwHH6.png)
![Imgur](https://i.imgur.com/gPu47EP.png)
![Imgur](https://i.imgur.com/K8QkTCm.png)

### Code I Used To Create My Database

Below are some of the SQL code snippets that I used to create my databse, they come under the following types:

#### Insert
This command is used to insert values and data into tables.

INSERT INTO ENEMIES VALUES( 
    1, 50,'MAGE', 150,'30'
);

INSERT INTO HEROES VALUES( 
    2, 20,'PALADIN', 150,'50'
);

INSERT INTO SPELLS VALUES( 
    1, 50,'FIREBALL', '150'
);

#### Create
This command is used to create new tables with new values.

CREATE TABLE ENEMIES(
         ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,
         NAME VARCHAR(50) NOT NULL,
         DAMAGE FLOAT NOT NULL,
         HP FLOAT NOT NULL
);

CREATE TABLE HEROES(
         ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,
         NAME VARCHAR(50) NOT NULL,
         CLASS VARCJAR(50) NOT NULL,
         HP FLOAT NOT NULL
);

CREATE TABLE SPELLS(
         ID INT NOT NULL PRIMARY KEY,
         DAMAGEHEALING INT NOT NULL,
         NAME VARCHAR(50) NOT NULL,
         RANGE INT NOT NULL,     
);

CREATE TABLE ENEMY_SKILLS(
         ENEMY_ID INT NOT NULL PRIMARY KEY,
         SPELL_ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,    
);

CREATE TABLE HERO_SKILLS(
         HERO_ID INT NOT NULL PRIMARY KEY,
         SPELL_ID INT NOT NULL PRIMARY KEY,
         LEVEL INT NOT NULL,    
);


#### Update
This command is used to update the value of data within a table without having to create a new table.

UPDATE HEROES
    SET LEVEL = 4
    WHERE ID = 1;
    
UPDATE HEROES
    SET DAMAGE = 12.4
    WHERE NAME = BOI;

UPDATE SPELLS
    SET RAGE = 4
    WHERE ID = 4;
   
UPDATE SPELLS
    SET DAMAGEHEALING = 4
    WHERE NAME = FIREBALL;
    
#### Delete
This command is used to delete values from tables, the type of data can be specified.

DELETE FROM ENEMIES WHERE ID=2
LEVEL > 2 AND NAME='DRAGON';

DELETE FROM ENEMIES WHERE NAME = 'MAGE';

DELETE FROM SPELLS WHERE RANGE = 50 ;

#### Select
This command is used to search the database for any data that matches the paramaters you inpud into the command, it will then return any found data that fits these paramaters to you.

SELECT H.CLASS, H.LEVEL, S.NAME, HS.LEVEL
FROM HERO H, SKILLS S, HERO_SKILLS HS
WHERE HS.HERO_ID = H.ID AND HS.SKILL_ID = S.ID
AND S.NAME LIKE 'Fire%';

SELECT * FROM HERO;

SELECT LEVEL, CLASS FROM HERO
WHERE ID = 2;

SELECT MAX(H.LEVEL), MIN(H.LEVEL) FROM HERO H;

SELECT AVG(H.LEVEL) FROM HERO H;

### User and Technical Documentation

User and Technical Manual

Table of Content

1.0 General Information
1.1 System Overview
1.2 The Role of Database Systems As...
1.2.1 Back-end Systems
1.2.2 E-Commerce
1.2.3 Data Mining Applications
1.3 Tools Used

2.0 System Summary
2.1 What Is An Object Oriented Database?
2.2 What Is The System For?


#### 1.0 General Information

##### 1.1 System Overview

This database system is designed to hold information on different characters that appear in the game. It has different tables for Heroes, Enemies and other tables relating to skills that hold all of the key values relating to that character, including Name, ID, Health and Damage. These values can be updated in real time for gameplay purposes.

##### 1.2 The Role Of Database Systems As…

Database systems can be used for a wide variety of things. The following is a list of different uses of database systems and what purpose they serve.

###### 1.2.1 Back-end Systems
	
A Back-End Database is a database that can be accessed by different users through a third-party application rather than by application programming stored within the database itself or by manipulation of the data.
	
###### 1.2.2 E-Commerce

In E-commerce, the main purpose of a database is to store information about the customer transactions, customer care, and inventory. By using a database,  programming a dynamic E-commerce website becomes easy as you only focus on the presentation and behavior of the website while all interactions are being managed by the system.

###### 1.2.3 Data Mining Applications

Data mining is the process of discovering patterns in large data sets using different methods. It is an essential process where intelligent methods are applied to extract data patterns. During the process of data mining, the database(s) are searched for key information that could uncover new patterns or sequences in the data.


##### 1.3 Tools Used

The following tools were used in the design and creation of the database system:

	-  draw.io 
	Used to create the Entity Relationship Diagram

	-  Microsoft Excel
	Used to create the data dictionary and the test plan documentation

	-  Microsoft Access
	Used to create the database system

 	-  Microsoft Word
	Used to create the user and technical documentation

#### 2.0 System Summary

##### 2.1 What Is An Object Oriented Database?

An object database is a database system in which data is represented in the form of objects similar in design to object oriented programming. Object databases are different from relational database which are table-oriented. Object-relational databases are a mix of both approaches. 

Object-oriented database management systems combine database capabilities with object oriented programming language capabilities. This design allows object-oriented programmers to develop the product, store them as objects, and duplicate and edit existing objects to make new objects Because the database is connected with the programming language, the programmer can maintain a high level of consistency, in that both the OODBMS and the programming language will use the same model to represent themselves. Relational database management system projects maintain a clearer division between the database model and the application.

##### 2.2 What Is The System For?

The system is designed to hold data on the status of different characters and spells within the game

### Testing the System

This is the test plan that we created to test our database system against:
![Imgur](https://i.imgur.com/LzUQA9j.jpg)

The following are screenshots showing evidence of our testing:

![Imgur](https://i.imgur.com/HiP8WgB.jpg)
![Imgur](https://i.imgur.com/DlWJkF3.jpg)
![Imgur](https://i.imgur.com/hcRZnYg.jpg)
![Imgur](https://i.imgur.com/ymRbWPC.jpg)
![Imgur](https://i.imgur.com/DaIjdro.jpg)
![Imgur](https://i.imgur.com/UYpVz2T.jpg)
![Imgur](https://i.imgur.com/gsOTjzC.jpg)
![Imgur](https://i.imgur.com/ynlwh3N.jpg)
![Imgur](https://i.imgur.com/NGN9Wqo.jpg)
![Imgur](https://i.imgur.com/YzzIUiM.jpg)
![Imgur](https://i.imgur.com/A8Iy6h1.jpg)
