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

#### Forms
These forms are used to input data to the database and also do delete entries from the database.

![Imgur](https://i.imgur.com/gPu47EP.png)
![Imgur](https://i.imgur.com/K8QkTCm.png)

#### Data Validation
Below is an error that occours if the user attempts to input an invalid type of data into the form.

![Imgur](https://i.imgur.com/2VKLbUe.jpg)

#### Report
This is a report of all of the data entries held in the databse in the enemies table and some selected statistics about each enemy.
![Imgur](https://i.imgur.com/g2yWyqd.jpg)

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


#### 1.1 System Overview

This database system is designed to hold information on different characters that appear in the game. It has different tables for Heroes, Enemies and other tables relating to skills that hold all of the key values relating to that character, including Name, ID, Health and Damage. These values can be updated in real time for gameplay purposes.

#### 1.2 The Role Of Database Systems As…

Database systems can be used for a wide variety of things. The following is a list of different uses of database systems and what purpose they serve.

##### 1.2.1 Back-end Systems
    
A Back-End Database is a database that can be accessed by different users through a third-party application rather than by application programming stored within the database itself or by manipulation of the data.
    
##### 1.2.2 E-Commerce

In E-commerce, the main purpose of a database is to store information about the customer transactions, customer care, and inventory. By using a database,  programming a dynamic E-commerce website becomes easy as you only focus on the presentation and behavior of the website while all interactions are being managed by the system.

##### 1.2.3 Data Mining Applications

Data mining is the process of discovering patterns in large data sets using different methods. It is an essential process where intelligent methods are applied to extract data patterns. During the process of data mining, the database(s) are searched for key information that could uncover new patterns or sequences in the data.


#### 1.3 Tools Used

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


#### 2.1 What Is An Object Oriented Database?

An object database is a database system in which data is represented in the form of objects similar in design to object oriented programming. Object databases are different from relational database which are table-oriented. Object-relational databases are a mix of both approaches. 

Object-oriented database management systems combine database capabilities with object oriented programming language capabilities. This design allows object-oriented programmers to develop the product, store them as objects, and duplicate and edit existing objects to make new objects Because the database is connected with the programming language, the programmer can maintain a high level of consistency, in that both the OODBMS and the programming language will use the same model to represent themselves. Relational database management system projects maintain a clearer division between the database model and the application.

#### 2.2 What Is The System For?

The system is designed to hold data on the status of different characters and spells within the game    




#### 3.0 Risks/contingencies 

3.1 Risks   

The risks of this database are in the design and development stage, a few possible risks for this database are:

Database not updating reports from forms and having the data stay the same,

The forms having different characters and integers entered within them that they are programmed for.

The tables not communicating with each other and not updating with each other,

Having any of the forms not show the information that the tables have,


#### 3.2 Contingencies

The risks can be managed by planning contincies in order to help risks be prevented, some of the contingencies that we used were:

Keeping multiple saves in case a change ruined the database,

Having an ERD so that the database would keep to a specific design,

Keeping code saved in order to inspect it if anything went wrong,

Testing every bit of code after it was executed to make sure it all worked well,

#### 4.0 Design Decisions  

The design of the database was decided when planning the database, we used ERD’s to plan and figure out what would be best for the database, this also meant that we could test to make sure the tables connecting with each other would work well when running together. 

Making the ERD’s required planning on how the database worked,  we looked at the requirements of the database and the functionality on it, this included how it would work, what it would be used for and why is it being made, looking at these questions allowed us to create a template that would suite all of the needs that needed to be addressed within the database.

#### 4.1 Key Factors Influencing Design   

The key factors for the design was the functionality of the database, since it was being made for a game to hold data on the characters and their skills, it meant that designing it would have to revolve around that, keeping to this meant that we were able to keep a key design in mind. 

#### 4.2 Functional Design Decisions

Being made for a game, it meant that the functionality must cater for the games needs, for example the database was made to hold data on heroes, villains and their skills that they had, so for this it meant that all parts of it needed to be addressed. The database was able to function at a point where it could hold all the data and be able to change it in order to keep the game running well.

#### 4.3 Database Management System Decisions 

The database was managed by Microsoft access, we used this software as it allowed us to use all the tools we needed in order to create the database as we wanted to, this included having SQL queries integrated within it, allowing a design document as well as forms allowing for real time updating for reports. Having these tools allowed us to create a successful website that fulfilled the requirements for our game.

#### 4.4 Security and Privacy Design Decision 

The database is a private database, this means that the only people that can access it are the people that are on the file that it is created on, this means that only the creator and anyone that they want to share it with have access to the database. This means that there cannot be any breaches of the data at this point in time.

#### 4.5 Performance and Maintenance Design Decisions   

The database is not big and has few requirements, the scope of the project was not big, this meant that performance wise the database is extremely quickly and maintenance is not difficult. The database had no need to be any bigger than it was, this meant that from the design stage, there was no need to make big decisions on the performance of the database.

#### 5.0 Detailed Database Design   

The database was made in order to cater for a game, for this we made 5 tables, having five meant that we could cover all the aspects of the database’s function, whilst also keeping it performance light and also keeping the maintenance low. The five tables were Heroes, Villains, Heroes_Skills, Villains_Skills and Skills, these were enough in order to cover all points of the database. The forms of the database make sure that the data that is stored on their is clear and has a place to update the reports more. The reports that are included are made in order for people to view the data currently stored in the tables, this data will update in real time from when the forms are changed.

#### 5.1 Data Software Objects and Resultant Data Structures 

For the forms, we have created buttons that allow the viewer to change the data that is stored within the tables, these allow the data to be updated from the forms easily, as well as this there is a delete or remove button that can also be used in order to remove part of the database. The data is structured so that the data can be updated and edited from anywhere other than the reports, this means that the reports are easier to see and collect information from and can be focused on viewing the data rather than editing it.  





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
